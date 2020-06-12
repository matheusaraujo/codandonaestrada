---
layout: post
title:  Web Assembly - O que será do futuro da internet
date:   2018-02-15 00:00:00 +0300
description: Publicado originalmente em dtidigital.com.br/blog/webassembly/
img: webassembly/background.jpg # Add image post (optional)
tags: [Programação]
---

A página que você está lendo nesse momento é um amontoado de HTML, CSS e JavaScript.
<a href="https://en.wikipedia.org/wiki/HTML" target="_blank">HTML</a> é o cara que dá forma pra página, 
<a href="https://en.wikipedia.org/wiki/Cascading_Style_Sheets" target="_blank">CSS</a> é o cara que a deixa bonitinha e 
<a href="http://blog.dtidigital.com.br/dicas-e-boas-praticas-com-javascript/" target="_blank">JS</a> é a linguagem de programação por trás disso tudo.

Você já ouviu falar sobre JavaScript? Parece pergunta de vendedor de canal de compras, mas não é. 
No <a href="http://githut.info/" target="_blank">GitHub</a>, essa é a linguagem com maior número de repositórios.

Há mais Frameworks JavaScript do que átomos no universo. Virtualmente toda pessoa desenvolvedora já escreveu um código em JavaScript.

<center>&bull; &bull; &bull;</center>

## E por que isso?
Bem, basicamente porque não é possível construir uma aplicação Web sem usar JavaScript. Sério isso? Sim, tão sério que até aplicações de celulares tem usado JavaScript, olha o <a href="http://blog.dtidigital.com.br/progressivewebapps/" target="_blank">PWA</a> aí.

<center>&bull; &bull; &bull;</center>

## E isso é um problema?
Cara, pra mim não. Eu gosto muito de JavaScript, muito mesmo. JavaScript é a linguagem que te dá liberdade suficiente pra fazer o que quiser da maneira que quiser. Olha o <a href="https://github.com/nodejs/node/wiki" target="_blank">NodeJs</a>, por exemplo. Mas como diria meu pai: com grandes liberdades, vem grandes responsabilidades.

Então se você é livre pra fazer o que quiser como quiser em JavaScript, você tem que saber muito bem o que está fazendo. E aqui começa o problema. Infelizmente nem sempre escrevemos bons códigos em JavaScript, e essa é uma verdade dolorida.

Você já parou pra pensar em como um código JavaScript é executado pelo Browser? Leia o próximo parágrafo correndo.

> O browser recebe o código ocorre a interpretação léxica o parser monta a árvore de execução o tradutor a converte em bytecode finalmente o interpretador executa o código.

Ficou cansado? Parece muita coisa? De maneira geral, é assim que uma <a href="https://developer.telerik.com/featured/a-guide-to-javascript-engines-for-idiots/" target="_blank">engine JavaScript</a> funciona. Acredite, esse processo já é bastante otimizado, cada passo desses é muito rápido. Só que esse processo acontece sempre, a cada requisição, a cada cliente da sua aplicação, esse processo se repete.

E aí vem a questão: já que o browser vai sempre fazer a mesma coisa pra transformar código em bytecode, por que eu não entrego bytecode direto pra ele?

<center>&bull; &bull; &bull;</center>
### O WebAssembly, ou WASM, entra aí.
Inclusive, olha uma palhinha do tech shot que eu dei na dti sobre WASM.

<center>
<iframe width="420" height="315"
    src="https://www.youtube.com/embed/8AvwLY5Q57I">
</iframe>
</center>

Vamos entregar o “Assembly” pra “Web”.

A ideia inicial era compilar o próprio código JavaScript e entregar pro navegador. No entanto, um efeito colateral interessante disso é que agora podemos escrever códigos em outras linguagens e entregar pro browser.

Então, se eu não gosto muito de JavaScript, agora eu posso escrever meu código C# e deixar que o browser rode o bytecode compilado a partir dele.

<center>&bull; &bull; &bull;</center>

## E isso funciona?
Funciona! <a href="https://github.com/matheusaraujo/Blazor" target="_blank">Olha esse repositório aqui no GitHub</a>. Ele é um fork que eu criei do projeto do Blazor do Steve Sanderson.

Com o Blazor, é possível escrever um código C# que vai rodar direto no browser.

Legal, cara, mas como isso vai tornar o mundo um lugar melhor?

Primeiro: as aplicações Web vão ficar mais rápidas, aquele processo todo que o browser faz vai ficar mais simples. Nesse <a href="https://d2jta7o2zej4pf.cloudfront.net/" target="_blank">link</a> você pode ver a comparação em tempo real entre um código WASM e um código JavaScript no processamento de imagem.

Segundo: agora você pode escolher sua linguagem preferida pra escrever sua aplicação, se você não gosta de JavaScript, sem problemas, escreva um bom código na linguagem com a qual você se sente mais confortável.

Atualmente, muito do que se faz em WebAssembly ainda é experimental, mas há quem acredite que esse seja o <a href="https://www.hanselman.com/blog/NETAndWebAssemblyIsThisTheFutureOfTheFrontend.aspx" target="_blank">futuro da Internet</a>.