# Classes Abstratas e Seladas

## Classes Abstratas

Uma classe abstrata não pode ser instanciada. A finalidade de uma classe abstrata é fornecer uma definição comum de uma classe base que pode ser compartilhada por várias classes derivadas.

```C#
public abstract class A
{
    // Class members here.
}
```

As classes abstratas também podem definir métodos abstratos. Isso é realizado através da adição da palavra-chave abstract antes do tipo de retorno do método. Por exemplo:

```C#
public abstract class A
{
    public abstract void DoWork(int i);
}
```

As classes derivadas da classe abstrata devem implementar todos os métodos abstratos.

## Classes Seladas

Uma classe selada não pode ser usada como uma classe base. Por esse motivo, também não pode ser uma classe abstrata. As classes selada impedem a derivação. Como elas nunca podem ser usadas como uma classe base, algumas otimizações em tempo de execução podem tornar a chamada a membros de classe selada ligeiramente mais rápida.

```C#
public sealed class D
{
    // Class members here.
}
```

## Referências

[Documentação Microsoft - Classes e membros de classes abstract e sealed](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members)