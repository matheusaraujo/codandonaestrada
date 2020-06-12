---
layout: post
title:  Banco de Dados Sybase, 5 Boas Práticas em.
date:   2018-01-08 00:00:00 +0300
description: Publicado originalmente em dtidigital.com.br/blog/banco-de-dados-sybase-boas-praticas-em/
img: banco-de-dados-sybase-boas-praticas-em/background.jpg # Add image post (optional)
tags: [Programação]
---

**_“Um pouco mais de conhecimento ilumina nosso caminho”_ – Mestre Yoda**. No post de hoje, sobre boas práticas para desenvolvimento em banco de dados Sybase ASE, falar iremos. Técnico, o assunto é; porém divertido ele também será, Jovem Padawan.

Algumas dicas para o desenvolvimento de Banco de Dados Sybase a seguir discutiremos!

## 1. No Banco de Dados Sybase, índices existir precisam.
Índices estão diretamente relacionados ao bom desempenho de um banco de dados. Eles são usados pelo otimizador para reduzir o tempo das consultas, mas devem ser atualizados a cada inserção, atualização ou exclusão de registro na tabela.

Portanto, a criação de um índice deve ser muito bem analisada.  Por exemplo, se uma tabela tem muitos registros (ordem de milhões) e eu praticamente só consulto a tabela (inserções são raras e não necessariamente precisam ser rápidas), a criação de um índice pode melhorar a performance da consulta na ordem de dezenas.

Mas ao contrário, se a coluna que é índice é atualizada constantemente em uma operação que deve ser rápida, a performance da inserção será pior do que se não houvesse índice. Portanto, nesse segundo caso, se a consulta não é realizada frequentemente e não tem requisitos fortes de performance, talvez a criação do índice seria desnecessária. O query plan de uma consulta é uma ferramenta de análise muito importante nesse caso.

**Use a força e a solução encontrará.**

## 2. Datatypes corretos usar você deve.
Eventualmente acontece de passarmos desapercebidos pelos tipos de variáveis nas consultas que fazemos.

A coluna no banco de dados é NUMERIC (10, 0) e quando montamos a consulta, usamos uma variável INT na cláusula WHERE. Aparentemente, os datatypes são equivalentes, mas o que acontece é que o otimizador não consegue usar índices nesse caso, e sua consulta vai ficar muito mais lenta. Muito mais lenta mesmo.

Em um dos casos em que atuamos, conseguimos reduzir o tempo médio da consulta em mais de 20 vezes, de 4 minutos para menos de 12 segundos, simplesmente corrigindo o tipo da variável na consulta.

Os 3 minutos e 48 segundos restantes podem ser acumulados e usados para assistir o episódio VII, por exemplo.

## 3. Funções boas são, evitadas em cláusulas WHERE e JOIN necessitam ser, porém.
Funções escalares aplicadas a uma coluna com índice impedem que o índice dessa coluna seja utilizado na cláusula WHERE, ou em um JOIN. O desempenho da sua consulta será comprometido, mesmo caso do item anterior.

## 4. BEGIN TRANS para tarde ficará, COMMIT/ROLLBACK para cedo ficará.
Em resumo, atrase o máximo possível o início de suas transações; e adiante o máximo possível o fim delas.

Isso porque transações custam caro para o banco, já que ele deve manter um controle muito mais rígido de seu estado interno. Se você abre uma transação e fica fazendo várias consultas de preparação para sua atualização, ele mantém um estado interno que pode ser desnecessário durante essas consultas.

## 5. Consultas executadas muito, SP substituir devem.
Consultas que são executadas com muita frequência ou que tenham o texto muito extenso podem ser substituídas por STORED PROCEDURES.

Com essa mudança, o tempo de compilação dos comandos SQL é reduzido e o tráfego de rede também.

**_“Por aqui o treinamento devo terminar”._**

Para todas suas perguntas, as respostas aqui você não encontrou, Jovem Padawan; mas lembrar-se de continuar estudando você deve; e, “sempre passar o que você aprendeu”, claro é.

_“Que a força esteja com você.”_