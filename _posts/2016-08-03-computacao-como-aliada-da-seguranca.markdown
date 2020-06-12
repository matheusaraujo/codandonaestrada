---
layout: post
title:  Segurança da Informação, o poder da computação
date:   2016-08-03 00:00:00 +0300
description: Publicado originalmente em dtidigital.com.br/blog/a-computacao-como-aliada-da-seguranca/
img: computacao-como-aliada-da-seguranca/background.jpg # Add image post (optional)
tags: [Programação]
---

Desde que os computadores deixaram de ocupar prédios inteiros e passaram a viver em nossos bolsos, ironicamente, temos dado cada vez mais espaço a essas tecnologias. É difícil pensar em alguma atividade do nosso cotidiano em que eles não estejam presentes. Há quanto tempo você não lê jornal? Aquele de papel que se compra na esquina. Quando foi a última vez que você parou num posto para pedir informação sobre como chegar a determinado lugar? Isso sem falar em cartas ou a angustiante espera pela revelação de fotos.

Esse processo de domesticação do computador tem acontecido de uma maneira tão natural, e tão rápida, que não estamos tendo tempo para pensar nele. Contudo, o texto de hoje não é pra ser uma reflexão sobre a computação em nosso cotidiano. Esse tema a gente deixa para a próxima prova do Enem (profecia!). 

**Hoje vamos falar sobre aplicações da computação em segurança e, sobre como essa relação, impensável há algum tempo, tornou-se essencial.**

<center>
<img src="/assets/img/computacao-como-aliada-da-seguranca/01.webp" alt="Códigos, códigos, códigos" />
</center>

## Os algoritmos e a segurança da informação
É bem provável que o seu banco já não use mais senhas alfanuméricas para operações em caixas rápidos. Você só precisa colocar o seu polegar numa placa de vidro com leitor laser e, como num livro do Asimov, depois de alguns milissegundos, tem acesso à sua conta. O que acontece ali não é mágica, claro. É só mais uma atividade do nosso cotidiano que foi modificada pelos computadores. **Depois de alguns anos estudando algoritmos de detecção de padrão, desenvolvendo sensores cada vez mais precisos, criando redes seguras e rápidas, fomos capazes de colocar a biometria em caixas eletrônicos espalhados pelo mundo.**

Aqui na dti, certa vez, fomos desafiados por um problema semelhante. Envolvia segurança, biometria, sistemas distribuídos geograficamente e agilidade. Nosso cliente precisava de um sistema que evitasse fraudes. Elas ocorriam com certa frequência e, quando aconteciam, os prejuízos eram grandes. O primeiro desafio foi tentar identificar um padrão nesses acontecimentos.

O ser humano é muito bom em detectar padrões. Desde quando vivíamos em cavernas, conseguíamos identificá-los no caos aparente. Foi através dessa nossa habilidade que conseguimos decifrar, por exemplo, como as estrelas se movem no céu. Através dessa constatação, percebemos que a posição das estrelas estava relacionada a um ciclo climático anual e, conhecendo este ciclo, deixamos de simplesmente estarmos sujeitos às intempéries do ambiente, e começamos a plantar, formar cidades.

Às vezes somos bons demais em reconhecer padrões, e isso pode ser um problema. E já que o tema de hoje é também astronomia, quem nunca ouviu falar daquelas teorias malucas de rosto humano em formação rochosa na Lua ou em Marte? Ou olhou para uma tomada de três pinos, daquelas antigas, e viu uma carinha assustada? O nome disso é pareidolia.

<center>
<img src="/assets/img/computacao-como-aliada-da-seguranca/02.webp" alt="Pareidolia" />
</center>

## Mas o que a pareidolia tem a ver com segurança ou com sistemas computacionais ultramodernos?

Tem a ver que começamos a ensinar os computadores a procurarem por esses padrões, e eles estão aprendendo bem.

Existem inúmeros algoritmos de detecção de padrão e, dentro dessa categoria, diversas subcategorias com outros tantos algoritmos. **De maneira bem geral e superficial, o que se faz é classificar o universo de informações de acordo com alguns critérios, e depois determinar quais critérios são relevantes na classificação e identificação de um elemento dentro desse universo.** A gente faz isso meio sem perceber.

Imagine o rosto de uma pessoa, um rosto comum sem nenhuma característica acentuada.

Agora tente descrevê-lo.

Você provavelmente irá falar sobre olhos, boca ou nariz. Essas são características marcantes que ajudam a distinguir as pessoas, e através das quais podemos diferenciar dois indivíduos ou até mesmo, reconhecer uma pessoa em fotos diferentes, por exemplo.  E, acredite, o computador faz isso usando muita matemática, e aquela piadinha de que o Teorema de Pitágoras não tem utilidade, cai por terra.

Mas e o nosso cliente lá atrás? Bom, conseguimos encontrar um padrão na ocorrência das fraudes, criamos um sistema que identificasse esse padrão de maneira autônoma e adaptativa, e o implementamos. E funcionou? Sim. Funciona até hoje. O sistema roda em mais de 1000 computadores diferentes e já conseguiu evitar fraudes e, consequentemente, prejuízos.