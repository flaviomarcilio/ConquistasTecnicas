# Construtores

Um construtor é um método cujo nome é igual ao nome de seu tipo e não possui um tipo de retorno. O construtor pode ter ou não parâmetros.

Um construtor padrão (sem parâmetros) sempre é definido para uma classe implicitamente. Entretanto, quando um construtor é definido explicitamente para a classe, o construtor padrão deixa de ser oferecido implicitamente, ou seja, se for definido um construtor com parâmetro para a classe e deseja utilizar também o construtor sem parâmetro, esse deve ser implementado na classe.

O exemplo a seguir mostra o construtor para uma classe denominada ``Person``.

```C#
public class Person
{
   private string last;
   private string first;

   public Person(string lastName, string firstName)
   {
      last = lastName;
      first = firstName;
   }

   // Remaining implementation of Person class.
}
```
## Construtor privado

Um construtor privado é um construtor de instância especial. Normalmente, ele é usado em classes que contêm apenas membros estáticos. Se uma classe tiver um ou mais construtores privados e nenhum construtor público, outras classes (exceto as classes aninhadas) não poderão criar instâncias dessa classe. 

Construtores privados são usados para impedir a criação de instâncias de uma classe quando não há métodos ou campos de instância, ou quando um método é chamado para obter uma instância de uma classe, como na classe ``Log``.

```C#
public class Log
{
    private static Log _log;

    private Log() { }

    public static Log GetInstance()
    {
        if (_log == null)
        {
            _log = new Log();
        }
        return _log;
    }
}
```

## Referências

[Documentação Microsoft - Constructors](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors)

[Volta](../README.md#construtores-propriedades-delegates-e-eventos-em-net)