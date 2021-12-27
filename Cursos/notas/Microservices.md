# Introdução a Microsserviços com .NET

## Monolitos x Microsserviços

![Monolith-Microservices](../images/monolith-microservices.jpg)

### Monolitos

A arquitetura monolítica é considerada uma forma tradicional de construção de aplicações. Uma aplicação monolítica é construída como uma unidade única e indivisível. Normalmente, essa solução compreende uma interface de usuário do lado do cliente, um aplicativo do lado do servidor e um banco de dados. Ele é unificado e todas as funções são gerenciadas e atendidas em um só lugar.

Normalmente, os aplicativos monolíticos têm uma grande base de código e não possuem modularidade. Se os desenvolvedores desejam atualizar ou alterar algo, eles acessam a mesma base de código. Portanto, eles fazem alterações em toda a pilha de uma vez. [1](#referências)

- Vantagens
  - Menos preocupações transversais: As preocupações transversais são aquelas que afetam todo o aplicativo, como registro, manipulação, armazenamento em cache e monitoramento de desempenho. Em um aplicativo monolítico, essa área de funcionalidade diz respeito a apenas um aplicativo, portanto, é mais fácil de manusear.
  - Depuração e teste mais fáceis: por ser uma única unidade indivisível, você pode executar testes de ponta a ponta com muito mais rapidez.
  - Simples de implantar: você não precisa lidar com muitas implantações - apenas um arquivo ou diretório.
  - Simples de desenvolver: qualquer equipe de engenharia tem o conhecimento e os recursos corretos para desenvolver um aplicativo monolítico.
- Desvantagens
  - Compreensão: Quando um aplicativo monolítico aumenta, torna-se muito complicado de entender. Além disso, um sistema complexo de código em um aplicativo é difícil de gerenciar.
  - Fazendo mudanças: É mais difícil implementar mudanças em um aplicativo tão grande e complexo com um acoplamento altamente rígido. Qualquer alteração no código afeta todo o sistema, portanto, deve ser totalmente coordenada. Isso torna o processo geral de desenvolvimento muito mais longo.
  - Escalabilidade: Você não pode dimensionar componentes de forma independente, apenas o aplicativo inteiro.
  - Novas barreiras de tecnologia: É extremamente problemático aplicar uma nova tecnologia em um aplicativo monolítico porque todo o aplicativo deve ser reescrito.
  - Problemas com merge-conflicts
  - Conexões simultâneas TCP é limitada
  - Deadlock e concorrência
  - Bugs e defeitos colaterais (único ponto de falha)
  - Build/deploy longos e demorados
  - Demora de aculturamento

### Microsserviços

> Resumindo, o estilo de arquitetura de microsserviço é uma abordagem para desenvolver um único aplicativo como um conjunto de pequenos serviços, cada um executando em seu próprio processo e se comunicando com mecanismos leves, geralmente uma API de recurso HTTP. Martin Fowler

- Vantagens
  - Componentes independentes: todos os serviços podem ser implantados e atualizados de forma independente, o que dá mais flexibilidade. Além disso, é muito mais fácil adicionar novos recursos a um aplicativo de microsserviço do que um monolítico.
  - Compreensão mais fácil: Dividido em componentes menores e mais simples, um aplicativo de microsserviço é mais fácil de entender e gerenciar. Você apenas se concentra em um serviço específico relacionado a uma meta de negócios que você tem.
  - Melhor escalabilidade: cada elemento pode ser dimensionado de forma independente.
  - Flexibilidade na escolha da tecnologia: As equipes de engenharia não são limitadas pela tecnologia escolhida desde o início. Eles são livres para aplicar várias tecnologias e estruturas para cada microsserviço.
  - Maior nível de agilidade: Qualquer falha em um aplicativo de microsserviços afeta apenas um serviço específico e não toda a solução. Portanto, todas as alterações e experimentos são implementados com riscos menores e menos erros.

- Desvantagens
  - Complexidade extra: Como uma arquitetura de microsserviços é um sistema distribuído, você deve escolher e configurar as conexões entre todos os módulos e bancos de dados. Além disso, desde que tal aplicativo inclua serviços independentes, todos eles devem ser implantados de forma independente.
  - Distribuição do sistema: Uma arquitetura de microsserviços é um sistema complexo de vários módulos e bancos de dados, portanto, todas as conexões devem ser tratadas com cuidado.
  - Preocupações transversais: Ao criar um aplicativo de microsserviços, você terá que lidar com uma série de questões transversais. Eles incluem configuração externalizada, registro, métricas, verificações de saúde e outros.
  - Testando: Uma infinidade de componentes implantáveis independentemente torna o teste de uma solução baseada em microsserviços muito mais difícil.

## Referências

1: [Microservices vs Monolith: which architecture is the best choice for your business?](https://www.n-ix.com/microservices-vs-monolith-which-architecture-best-choice-your-business/)<br>
2: [Microservices](https://martinfowler.com/articles/microservices.html)