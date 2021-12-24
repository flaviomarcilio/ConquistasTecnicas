# Interfaces

Uma interface contém definições para um grupo de funcionalidades relacionadas que uma classe não abstrata ou um struct deve implementar. Uma interface pode definir métodos estáticos, que devem ter uma implementação. A partir do C# 8.0, uma interface pode definir uma implementação padrão para membros. Uma interface não pode declarar dados de instância, como campos, propriedades implementadas automaticamente ou eventos de propriedade.

Usando interfaces, você pode, por exemplo, incluir o comportamento de várias fontes em uma classe. Essa funcionalidade é importante em C# porque a linguagem não dá suporte a várias heranças de classes. Além disso, use uma interface se você deseja simular a herança para structs, pois eles não podem herdar de outro struct ou classe.

Você define uma interface usando a palavra-chave ``interface`` como mostra o exemplo a seguir.

```C#
interface IEquatable<T>
{
    bool Equals(T obj);
}
```

Por convenção, os nomes de interface começam com uma letra maiúscula ``I``.

## Referências

[Documentação Microsoft - Interfaces - definir comportamento para vários tipos](https://docs.microsoft.com/pt-br/dotnet/csharp/fundamentals/types/interfaces)