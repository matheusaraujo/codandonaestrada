---
layout: post
title:  Compartilhando sessão entre aplicações NET Web em domínios diferentes
date:   2018-01-29 00:00:00 +0300
description: Publicado originalmente em dtidigital.com.br/blog/compartilhando-sessao-entre-aplicacoes-net-web-em-dominios-diferentes/
img: compartilhando-sessao-entre-aplicacoes-net-web-em-dominios-diferentes/background.jpg # Add image post (optional)
tags: [Programação]
---

**ATENÇÃO: O conteúdo apresentado a seguir é estritamente técnico. Não existem estudos sobre os danos que sua leitura pode causar aos não-programadores. No entanto, há fortes indícios para crermos que ela faça muito bem aos entusiastas de aplicações NET Web.**

Quando analisamos o atual contexto do desenvolvimento Web, é bastante comum perceber que os sistemas estão distribuídos entre aplicações diferentes. Da mesma forma, estas aplicações também acabam alocando-se em servidores de domínios diversos.

Em um de nossos projetos, trabalhamos em um sistema legado que era distribuído entre duas aplicações diferentes, em servidores diferentes. De um lado havia um site SharePoint. Do outro, uma aplicação MVC padrão. Nosso desafio era criar a funcionalidade de usuário no sistema e mantê-lo logado ao mesmo tempo nas duas aplicações.

Para aplicações .NET, as informações de sessão do usuário ficam armazenadas nos servidores. No cliente (browser) é armazenado apenas o identificador da sessão (SessionID) em <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies" target="_blank">Cookie</a>.

## E aí começa o problema…
A cada requisição que o cliente faz para o servidor, é necessário enviar o SessionID utilizado.

Nas requisições onde a página web está no mesmo domínio do servidor, essa informação é enviada normalmente, sem problemas. Você é feliz e nem percebe o que está acontecendo por trás disso tudo.

Para o cenário do nosso caso, em que o sistema está distribuído em aplicações diferentes, em domínios diferentes (parte em http://sharepoint.acme.com e outra parte em http://mvc.acme.com) existe uma solução bastante conhecida: as Requisições <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS" target="_blank">HTTP Cross-site</a>.

O CORS funciona sem complicações. Dá um pouco de trabalho implementar, mas você consegue viver bem com ele…  Até o momento em que seu tio chato com o mesmo computador há dez anos precisa acessar o sistema pelo Internet Explorer 8.

Ele vai até entrar no http://sharepoint.acme.com, depois ver uns botões que eram quadrados agora um pouco mais arredondados, mas vai ver. O chato é que quando ele tentar fazer qualquer coisa que precise do http://mvc.acme.com. **_TCHARAM_** seu sistema simplesmente não faz nada. E não adianta olhar no Fiddler, a requisição simplesmente não é feita.

Para o IE8, existe o XDomainRequest, uma alternativa para o CORS. A requisição chega a ser enviada, no entanto os cookies não são enviados, fato que não soluciona nosso problema inicial de manter a sessão.

Com isso você pensa:

> eu compro outro computador pro meu tio mala ou quebro a cabeça mais um pouco?

Bom, você é programador (ou, se chegou até aqui, entusiasta pelo menos), não tem dinheiro e gosta de se divertir com esse tipo de coisa. Então, vamos pensar mais um pouco.

O princípio do CORS é fazer a comunicação entre duas aplicações em domínios diferentes através de requisições HTTP. Então você se lembra daquele professor de filosofia do ensino médio que te ensinava a rever seus princípios e descarta requisições HTTP.

Bom, qual seria a próxima opção então? COM+, Socket, OLE ou Sinal de Fumaça? Nada disso, vamos pelo que a gente já sabe e domina: JavaScript.

Sim, JavaScript! A linguagem oferece um recurso de comunicação entre aplicações rodando em domínios diferentes, o <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage" target="_blank">postMessage</a>.

E como resolver o problema da requisição então? Nas requisições comuns, você envia uma mensagem pro servidor, espera um tempo e ele responde. Quando ele responde você faz uma alguma coisa, representando por um mini-diagrama:

<center>
<img src="/assets/img/compartilhando-sessao-entre-aplicacoes-net-web-em-dominios-diferentes/01.webp" alt="Diagrama" />
</center>

Voltando ao nosso sistema. FuncaoA() e funcaoB() estão no domínio http://sharepoint.acme.com, e enviam e recebem respostas do servidor no mesmo domínio. Então sem problemas, caminho feliz.

Caso você precisasse fazer uma requisição para o http://mvc.acme.com, via postMessage, o caminho seria mais ou menos assim:

<center>
<img src="/assets/img/compartilhando-sessao-entre-aplicacoes-net-web-em-dominios-diferentes/02.jpg" alt="Diagrama" />
</center>

Parece confuso, mas não é esse absurdo (diga lá, alguns algoritmos de programação dinâmica são bem piores). O que acontece aqui é que existe uma camada de comunicação no JavaScript entre as aplicações nos domínios diferentes.

Então, em vez de um JavaScript fazer uma requisição direta pra um servidor em outro domínio, ele faz a requisição para um outro JavaScript no domínio do segundo. O segundo JavaScript se encarrega de comunicar com o servidor: quando o servidor responde, ele simplesmente repassa a resposta para o Javascript que o chamou.

**Pronto! Agora seu tio do IE8 pode usar seu sistema feliz.**

Se ainda ficar com alguma dúvida, existe um exemplo bem legal de implementação dessa ideia nesse <a href="http://blog.teamtreehouse.com/cross-domain-messaging-with-postmessage">link</a>.

**Boa Sorte!**