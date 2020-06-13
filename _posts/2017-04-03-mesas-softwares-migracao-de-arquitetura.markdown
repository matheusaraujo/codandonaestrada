---
layout: post
title:  Sobre mesas, softwares e migração de arquitetura
date:   2017-04-03 00:00:00 +0300
description: Publicado originalmente em dtidigital.com.br/blog/sobre-mesas-softwares-e-migracao-de-arquitetura/
img: mesas-softwares-migracao-de-arquitetura/background.jpg # Add image post (optional)
tags: ["Computação"]
---

Quando entrei na dti, tive meu primeiro contato com o mundo ágil e um dos primeiros ensinamentos que tive de um de nossos Jedis foi:

> Fábrica de software não somos nós, fabril não é nosso fazer, artesanato se assemelha mais.

Levei um tempo para entender o que ele queria dizer com isso. Pra tentar explicar o que entendi, vou fazer um paralelo entre mesas e softwares.

## Inicial e conceitualmente, o que é uma mesa?
Segundo a <a href="https://pt.wikipedia.org/wiki/Mesa" target="_blank">Wikipédia</a>: 

> Mesas podem ser de jantar, mesas de centro, mesas de cozinha, mesas de jardim, mesas de reunião, mesas de bar, antigas, clássicas, modernas, ou contemporâneas, variando sua forma conforme o uso e utilidade local.

## Ok. E um software?
Segundo a <a href="https://pt.wikipedia.org/wiki/Software" target="_blank">Wikipédia</a> também: 

> Um programa de computador é composto por uma sequência de instruções, que é interpretada e executada por um processador ou por uma máquina virtual. Em um programa correto e funcional, essa sequência segue padrões específicos que resultam em um comportamento desejado.

## E o que uma coisa tem a ver com a outra? E a migração de arquitetura?
É difícil pensar “o que” é uma mesa sem pensar em “para que” ela serve, ou seja, a mesa é um meio pra realizarmos um fim. Usamos mesas para comer, para estudar, trabalhar, ornamentar, socializar e várias outras coisas. A mesa em si, só faz sentido, quando tem utilidade.

E um software? Basicamente, é a mesma coisa. Um software por si só não faz sentido, se não tiver uma utilidade.

/*Acho, inclusive, que podemos estender essa ideia para o computador em si — seja ele um desktop ou um smartphone — mas vamos nos ater ao que a gente sabe fazer. */

Bom, já concordamos que softwares são mesas (ou não, sei lá). Mas vamos voltar à conversa de fábrica de software versus ateliê de software.

## Como as mesas são feitas? Depende do propósito, você vai dizer.
As mesas dos botecos que você frequenta depois de programar o dia todo são de plástico e feitas numa fábrica. Mas a mesa que você (ou sua namorada||namorado||esposa||marido) sonha colocar na sala de jantar é planejada por um arquiteto ou designer e construída por algum especialista, um artesão ou marceneiro, talvez. Provavelmente, essa mesa tem o tampo de vidro de Murano ou os pés de um Mogno da Amazônia.

Tanto a mesa do boteco, quanto a mesa de mogno amazônico são, mesas. Ambas atendem aos requisitos necessários e são boas nisso. Você não pode dizer que a mesa da sala é melhor que a mesa do boteco. O valor financeiro não pode ser o critério de comparação aqui, porém a capacidade de resolver um problema proposto.

## E o software?
Novamente, a mesma coisa. Existem muitos softwares e muitas formas diferentes de construir software. Uma é melhor que a outra? Depende. Você não vai querer receber seus amigos em casa para um jantar numa mesa de boteco, e uma mesa de vidro num boteco acabaria quebrada.

**A questão, portanto, é em que situação uma forma é mais adequada do que a outra.**

<center>&bull; &bull; &bull;</center>

## Tá, mas e a fábrica/ateliê?
Construir um software quase nunca é seguir uma linha fordista de manufatura. Não é uma sequência de passos onde você pega uma tela, coloca um campo de texto e um botão, monta um servidor Rest e depois cola tudo com Ajax e JSON.

Existem alguns softwares assim, e eles atendem muitos casos, mas quando falamos de sistemas robustos que devem responder de maneira rápida e segura, que terão muitos usuários espalhados pelo mundo, a coisa fica um pouco mais complicada.

Para esses sistemas, você vai precisar de alguém que entenda sua necessidade e o espaço que você tem. Juntando isso ao valor que você quer investir, esse cara vai desenhar o protótipo de uma solução. Depois, uma equipe com habilidades para isso, vai transformar esse protótipo em uma solução de fato. Esses caras vão usar bastante raciocínio lógico, um monte de café e, no fim, terão um código fonte que é o seu software.

O risco dessa perspectiva da criação de software é pensarmos que o artesão vai construir seu produto sem seguir nenhum padrão e de uma maneira arbitrária.

Bom, mais ou menos. Um bom artesão vai tentar encontrar uma boa técnica de cortar um pedaço de tronco bruto de forma que consiga a peça final na medida necessária usando o mínimo da madeira.

Na construção de software temos boas práticas de código limpo, testes automatizados, metodologias ágeis, entre outros mecanismos que são ferramentas essenciais ao processo.

A questão, nos dois cenários, é que a ação humana move a coisa, e a capacidade de realizar essa ação envolve habilidade, é claro, mas envolve também bastante estudo, criatividade, esforço e capacidade de enxergar soluções.

<center>&bull; &bull; &bull;</center>

## Vamos falar sobre o Java Spring e o AngularJS?
_**Aviso aos não-técnicos e aos sem-tempo:** a partir do próximo parágrafo esse texto se transformará num enfadonho relatório técnico. Caso queira parar nesse ponto, obrigado por ter vindo até aqui; caso continue, não vá dizer que eu não avisei!_

Recentemente na dti fomos submetidos a um desafio de melhorar a usabilidade e tempo de resposta de um sistema Web construído em Java, que usava Spring e JSF.

Entre os diversos requisitos desse desafio, havia um que era manter tudo que fosse possível da arquitetura estabelecida. Deveríamos manter a implementação das regras de negócio e também a identidade visual após a migração de arquitetura. Outro requisito era usar algum Framework em JavaScript.

<center>
<img src="/assets/img/mesas-softwares-migracao-de-arquitetura/01.png" alt="Arquitetura convencional" />
</center>

## Ok. E agora, José?
A gente precisava mudar o sistema, mas usando o mesmo sistema. Entendeu?

E foi aí que nosso lado artesão apareceu. Pensamos: vamos separar o que dá pra separar e ir ajustando parte a parte. Se fosse a mesa, separaríamos os pés do tampo, e iríamos melhorando o que era necessário e possível em cada parte.

Inicialmente, fizemos a separação óbvia: cliente e servidor. No servidor, procuramos identificar os métodos que consumiam mais tempo usando <a href="https://newrelic.com/" target="_blank">NewRelic</a> e fizemos as otimizações possíveis.

No lado do cliente a coisa foi legal: a proposta era utilizar AngularJS. Já falamos sobre Angular aqui no <a href="http://blog.dtidigital.com.br/angular-js-uma-introducao/" target="_blank">blog da dti</a>.

Para fazer a “inserção” do Angular no JSF, usamos métodos não muito “ortodoxos”. Seria inviável e demorado recriar toda a estrutura das páginas, com o controle de permissão, os cabeçalhos e rodapés, além das mensagens de notificação que eram exibidas de tempos em tempos para o usuário.

O que fizemos foi criar um template do JSF que aceitasse o Angular. As páginas que foram recriadas herdavam esse template que tinha tudo o que iríamos manter do sistema antigo, mas abriam a possibilidade de inserirmos o Angular.

<center>
<img src="/assets/img/mesas-softwares-migracao-de-arquitetura/02.png" alt="Arquitetura modificada" />
</center>

## Mas isso é um Frankstein, você pode dizer.
Mais ou menos. Encontrar soluções que sejam tecnicamente corretas e economicamente viáveis é um desafio diário. Usando essa solução, conseguimos manter uma parte grande do sistema (economicamente viável) e conseguimos incluir o Angular sem grandes estragos (tecnicamente correto). Bela migração de arquitetura!

O interessante dessa solução é que o usuário final não sabia o que estava acontecendo por trás do sistema, pois visualmente não fez nenhuma diferença. O usuário não faz a menor ideia do que seja JSF ou Angular, mas ele percebe que uma tela é mais rápida e amigável que a outra; uma usa Angular, a outra não.

Para que a identidade visual fosse mantida, usamos outra habilidade de artesão: fizemos cópias dos arquivos .css usados no sistema e adequamos para os componentes que criamos, ajustando apenas os nomes das classes.

E para “colar” o Angular ao restante do sistema, criamos um servidor Rest usando Spring que fazia uma espécie de “fachada” entre o backend e o frontend. Ou seja, mantivemos toda a implementação de regras de negócio e persistência de dados já implementada.

### E aí, você proporia outra solução pra esse desafio?

> “A arte de programar consiste na arte de organizar e dominar a complexidade.”
Edsger W. Dijkstra