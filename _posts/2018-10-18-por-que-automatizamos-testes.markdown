---
layout: post
title:  Por que automatizamos testes?
date:   2018-10-18 00:00:00 +0300
description: Publicado originalmente em medium.com/@matheus.saraujo/por-que-automatizamos-testes-760c113f3bd0
img: por-que-automatizamos-testes/background.jpeg # Add image post (optional)
tags: [Programação, Automação de testes]
---

Uma metáfora recorrente (apesar de bélica) para comparar o desenvolvimento de software com outras engenharias é a diferenciação entre uma catapulta e um míssil teleguiado.

A catapulta mira um alvo estático. Em seu desenvolvimento, há um longo tempo de planejamento, projeto, construção … e só então o projétil é lançado. O trajeto feito pelo projétil será aquele definido pelo lançamento e pelas condições do ambiente, sem possibilidade de adaptação. Com sorte acertamos o alvo.

Desenvolver software se assemelha a lançar um míssil teleguiado. Pra começar, o alvo pode estar se movendo. O míssil precisa adaptar sua trajetória pra acertá-lo. E ainda que o alvo não se mova, outros elementos (como um sistema antimíssil) podem tentar impedir que o míssil chegue ao alvo. Novamente, ele precisa adaptar sua trajetória para ter sucesso.

<center>&bull; &bull; &bull;</center>

Nesse cenário de tentarmos atingir um alvo em movimento com fatores externos agindo em sentido contrário, fica claro que nosso sistema precisa ser adaptável, resiliente, flexível e evoluível.

Então vamos falar de software propriamente.

- Estamos desenvolvendo **sistemas adaptáveis**: os requisitos e regras de negócio que nosso software atende mudam ao longo do tempo.
- Estamos desenvolvendo **sistemas resilientes**: os softwares que desenvolvemos serão submetidos a situações adversas, um usuário inexperiente, uma sobrecarga de requisições, ou mesmo um ataque.
- Estamos desenvolvendo **sistemas flexíveis**: os sistemas que desenvolvemos irão rodar em diferentes dispositivos, serão usados por diferentes usuários.
- Estamos desenvolvendo **sistemas evoluíveis**: novas tecnologias estão surgindo o tempo todo, nossos sistemas podem/devem evoluir com elas.

Legal, mas isso tudo está relacionado a _agilidade_, até agora não falamos em testes, muito menos em automação de testes. Ledo engano. A automação de testes é a habilitadora pra todos esses itens.

- **Testes funcionais** vão garantir que regras de negócio estão ou não estão sendo atendidas. À medida que as regras e requisitos são alterados — e o código é alterado por consequência — podemos usar esses testes para garantir que a aplicação continua fazendo o que precisa ser feito.
- **Testes de performance e testes de segurança** (system tests) ajudam a garantir o funcionamento da aplicação em situações adversas.
- **Testes de usabilidade** são úteis, por exemplo, pra testar um mesmo site em diferentes navegadores.
- **Testes unitários** são ótimas ferramentas de auxílio em evoluções do código. Imagine que você refatorou uma função no meio da sua camada de regras de negócio, a forma mais rápida de garantir que sua refatoração não quebrou nada é com testes unitários.

Além desses, há vários outros tipos de testes: de configuração, de instalação, de integridade, de integração, de volume, de caixa preta, de regressão, de manutenção. Eles estão resumidos na pirâmide de testes:

<center>
<img src="/assets/img/por-que-automatizamos-testes/background.jpeg" alt="Pirâmide de testes" />
</center>

<center>&bull; &bull; &bull;</center>

O objetivo da automação de testes é, portanto, viabilizar o desenvolvimento ágil de software. Podemos fazer todos esses testes manualmente, mas isso é moroso e tedioso. Se queremos entregar software em produção a cada duas semanas, não podemos consumir uma semana testando. Mas lembre-se:

> Testes são código!

Você é programador, você testa seu código. Se testes são código, você pode escrever um código faça esse trabalho por você. Simples assim.

<center>&bull; &bull; &bull;</center>

Começar a automação de testes em um projeto que já está em desenvolvimento com certeza é mais difícil do que começar um projeto novo usando TDD ou outras técnicas de testes. Mas isso não quer dizer que você não precisa testar esse projeto que já está sendo desenvolvido.

> Code without tests is bad code. It doesn’t matter how well written it is; it doesn’t matter how pretty or object-oriented or well-encapsulated it is. With tests, we can change the behavior of our code quickly and verifiably. Without them, we really don’t know if our code is getting better or worse. **_Michael C. Feathers_ Working Effectively with Legacy Code**

Para representar esse processo de incluir testes em um código legado, criamos uma PoC, ela está disponível nesse <a href="https://github.com/matheusaraujo/PoC.TesteAutomatizado/" target="_blank">repositório do github</a>.

<center>&bull; &bull; &bull;</center>

Pra finalizar em três tópicos:

- “A única forma de ter uma solução de software com estabilidade sustentável é com alto nível de implementação de testes automatizados e DevOps.”
- Testes são código.
- Existem vários tipos de teste e várias formas de testar seu código, você precisa entender a necessidade do seu projeto, as razões por que testar e encontrar a que melhor se encaixa em sua realidade.