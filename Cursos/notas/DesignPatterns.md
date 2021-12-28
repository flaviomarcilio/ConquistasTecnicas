# Introdução a Design Patterns com .NET

## O que é Design Pattern

> Os padrões de projeto são soluções típicas para problemas comuns em projeto de software. Cada padrão é como um modelo que você pode personalizar para resolver um determinado problema de projeto em seu código. [1](#referências)

São soluções elegantes, testadas e aprovadas para problemas recorrentes que temos no design e implementação de software. Surgiram da experimentação e repetição.

## Padrões GoF

**Padrão de criação (Creational Pattern)**

Os padrões de criação são aqueles que abstraem e/ou adiam o processo criação dos objetos. Eles ajudam a tornar um sistema independente de como seus objetos são criados, compostos e representados. [2](#referências)

- Padrões criacionais
  - [Factory Method](https://refactoring.guru/design-patterns/factory-method): fornece uma interface para a criação de objetos em uma superclasse, mas permite que as subclasses alterem o tipo de objetos que serão criados.
  - [Abstract Factory](https://refactoring.guru/design-patterns/abstract-factory): permite produzir famílias de objetos relacionados sem especificar suas classes concretas.
  - [Builder](https://refactoring.guru/design-patterns/builder): permite construir objetos complexos passo a passo. O padrão permite que você produza diferentes tipos e representações de um objeto usando o mesmo código de construção.
  - [Prototype](https://refactoring.guru/design-patterns/prototype): permite copiar objetos existentes sem tornar seu código dependente de suas classes.
  - [Singleton](https://refactoring.guru/design-patterns/singleton): permite que você garanta que uma classe tenha apenas uma instância, enquanto fornece um ponto de acesso global para essa instância.

**Padrão estrutural (Structural Pattern)**

Os padrões estruturais se preocupam com a forma como classes e objetos são compostos para formar estruturas maiores. Os de classes utilizam a herança para compor interfaces ou implementações, e  os de objeto descrevem maneiras de compor objetos para obter novas funcionalidades. A flexibilidade obtida pela composição de objetos provém da capacidade de mudar a composição em tempo de execução o que não é possível com a composição estática (herança de classes). [2](#referências)

- Padrões estruturais
  - [Adapter](https://refactoring.guru/design-patterns/adapter): permite que objetos com interfaces incompatíveis colaborem.
  - [Bridge](https://refactoring.guru/design-patterns/bridge): permite dividir uma grande classe ou um conjunto de classes intimamente relacionadas em duas hierarquias separadas - abstração e implementação - que podem ser desenvolvidas independentemente uma da outra.
  - [Composite](https://refactoring.guru/design-patterns/composite): permite compor objetos em estruturas de árvore e, em seguida, trabalhar com essas estruturas como se fossem objetos individuais.
  - [Decorator](https://refactoring.guru/design-patterns/decorator): permite anexar novos comportamentos a objetos, colocando esses objetos dentro de objetos de invólucro especiais que contêm os comportamentos.
  - [Facade](https://refactoring.guru/design-patterns/facade): fornece uma interface simplificada para uma biblioteca, uma estrutura ou qualquer outro conjunto complexo de classes.
  - [Flyweight](https://refactoring.guru/design-patterns/flyweight): permite ajustar mais objetos na quantidade disponível de RAM, compartilhando partes comuns de estado entre vários objetos, em vez de manter todos os dados em cada objeto.
  - [Proxy](https://refactoring.guru/design-patterns/proxy): permite fornecer um substituto ou espaço reservado para outro objeto. Um proxy controla o acesso ao objeto original, permitindo que você execute algo antes ou depois que a solicitação chega ao objeto original.

**Padrão comportamental (Behavioral Pattern)**

Os padrões de comportamento se concentram nos algoritmos e atribuições de responsabilidades entre os objetos. Eles não descrevem apenas padrões de objetos ou de classes, mas também os padrões de comunicação entre os objetos. Os padrões comportamentais de classes utilizam a herança para distribuir o comportamento entre classes, e os padrões de comportamento de objeto utilizam a composição de objetos em contrapartida a herança. Alguns descrevem como grupos de objetos que cooperam para a execução de uma tarefa que não poderia ser executada por um objeto sozinho. [2](#referências)

- Padrões comportamentais
  - [Chain of Responsability](https://refactoring.guru/design-patterns/chain-of-responsibility): permite que você passe solicitações ao longo de uma cadeia de manipuladores. Ao receber uma solicitação, cada manipulador decide processar a solicitação ou passá-la para o próximo manipulador na cadeia.
  - [Command](https://refactoring.guru/design-patterns/command): transforma uma solicitação em um objeto autônomo que contém todas as informações sobre a solicitação. Essa transformação permite passar solicitações como argumentos de método, atrasar ou enfileirar a execução de uma solicitação e oferecer suporte a operações que podem ser desfeitas.
  - [Iterator](https://refactoring.guru/design-patterns/iterator): permite percorrer os elementos de uma coleção sem expor sua representação subjacente (lista, pilha, árvore, etc.).
  - [Mediator](https://refactoring.guru/design-patterns/mediator): permite reduzir dependências caóticas entre objetos. O padrão restringe as comunicações diretas entre os objetos e os força a colaborar apenas por meio de um objeto mediador.
  - [Memento](https://refactoring.guru/design-patterns/memento): permite salvar e restaurar o estado anterior de um objeto sem revelar os detalhes de sua implementação.
  - [Observer](https://refactoring.guru/design-patterns/observer): permite definir um mecanismo de inscrição para notificar vários objetos sobre quaisquer eventos que acontecem ao objeto que eles estão observando.
  - [State](https://refactoring.guru/design-patterns/state): permite que um objeto altere seu comportamento quando seu estado interno muda. Parece que o objeto mudou sua classe.
  - [Strategy](https://refactoring.guru/design-patterns/strategy): permite definir uma família de algoritmos, colocar cada um deles em uma classe separada e tornar seus objetos intercambiáveis.
  - [Template Method](https://refactoring.guru/design-patterns/template-method): define o esqueleto de um algoritmo na superclasse, mas permite que as subclasses substituam etapas específicas do algoritmo sem alterar sua estrutura.
  - [Visitor](https://refactoring.guru/design-patterns/visitor): permite separar algoritmos dos objetos nos quais operam.

## Referências

1: [Design Pattern](https://refactoring.guru/design-patterns)<br>
2: [Wikipédia - Padrão de projeto de software](https://pt.wikipedia.org/wiki/Padr%C3%A3o_de_projeto_de_software)