# Fundamentos de Coleções e LINQ com .NET

## [Array](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/)

Array é uma estrutura de dados para armazenar várias variáveis do mesmo tipo. Um array é declarado especificando o tipo de seus elementos.

```C#
type[] arrayName;
```

Um array tem as seguintes propriedades:

- Um array pode ser unidimensional, multidimensional ou denteado.
- O número de dimensões e o tamanho de cada dimensão são estabelecidos quando a instância do array é criada. Esses valores não podem ser alterados durante o ciclo de vida da instância.
- Os valores padrão dos elementos de um array numérico são definidos como zero e os elementos de referência são definidos como ``null``.
- Um array denteado é um array de arrays e, portanto, seus elementos são tipos de referência e são inicializados como ``null``.
- Os arrays são indexados por zero: um array com ``n`` elementos é indexado de ``0`` até ``n-1``.
- Os elementos do array podem ser de qualquer tipo, inclusive um tipo de array.
- Os tipos de array são tipos de referência derivados do tipo base abstrato ``Array``. Todos os arrays implementam ``IList`` e ``IEnumerable``. Você pode usar a instrução ``foreach`` para iterar por meio de um array. Arrays unidimensionais também implementam ``IList<T>`` e ``IEnumerable<T>``.


### Declarando e Instanciando um Array

A declaração e instanciação de um array pode ser feita como apresentado nos exemplos:

```C#
class TestArraysClass
{
    static void Main()
    {
        // Declare a single-dimensional array of 5 integers.
        int[] array1 = new int[5];

        // Declare and set array element values.
        int[] array2 = new int[] { 1, 3, 5, 7, 9 };

        // Alternative syntax.
        int[] array3 = { 1, 2, 3, 4, 5, 6 };

        // Declare a two dimensional array.
        int[,] multiDimensionalArray1 = new int[2, 3];

        // Declare and set array element values.
        int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

        // Declare a jagged array.
        int[][] jaggedArray = new int[6][];

        // Set the values of the first array in the jagged array structure.
        jaggedArray[0] = new int[4] { 1, 2, 3, 4 };
    }
}
```

### Manipulando Arrays

A classe ``Array`` fornece métodos para criar, manipular, pesquisar e classificar arrays, servindo assim como a classe base para todos os arrays no common language runtime.

A classe ``Array`` não faz parte dos namespaces ``System.Collections``. No entanto, ainda é considerado uma coleção porque é baseado na interface ``IList``.

## [Coleções](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections)

Os arrays são mais úteis para criar e trabalhar com um número fixo de objetos fortemente tipados. Por outro lado, as coleções fornecem uma maneira mais flexível de trabalhar com grupos de objetos. Ao contrário dos arrays, o grupo de objetos com que você trabalha pode aumentar e diminuir dinamicamente conforme as necessidades do aplicativo mudam. Para algumas coleções, você pode atribuir uma chave a qualquer objeto colocado na coleção para que possa recuperar rapidamente o objeto usando a chave.

Uma coleção é uma classe, portanto, você deve declarar uma instância da classe antes de adicionar elementos a essa coleção.

Se sua coleção contém elementos de apenas um tipo de dados, você pode usar uma das classes no namespace ``System.Collections.Generic``. Uma coleção genérica impõe segurança de tipo para que nenhum outro tipo de dados possa ser adicionado a ela. Ao recuperar um elemento de uma coleção genérica, não é necessário determinar seu tipo de dados ou convertê-lo.

### [Listas](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?view=net-6.0)

A classe genérica ``List<T>`` representa uma lista fortemente tipada de objetos que podem ser acessados por índice. Fornece métodos para pesquisar, classificar e manipular listas.

```C#
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

### [Filas](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1?view=net-6.0)

A classe ``Queue<T>`` é uma coleção de objetos que obedecem a regra FIFO (First-in, First-out), ou seja, o primeiro elemento adicionado é o primeiro elemento a ser retirado. Exemplo: Fila de banco.

```C#
Queue<string> numbers = new Queue<string>();
numbers.Enqueue("one");
numbers.Enqueue("two");
numbers.Enqueue("three");
numbers.Enqueue("four");
numbers.Enqueue("five");

// A queue can be enumerated without disturbing its contents.
foreach( string number in numbers )
{
    Console.WriteLine(number);
}

```

Esta classe implementa uma fila genérica como uma matriz circular. Os objetos armazenados em uma ``Queue<T>`` são inseridos em uma extremidade e removidos da outra. Filas e pilhas são úteis quando você precisa de armazenamento temporário para informações; ou seja, quando você deseja descartar um elemento após recuperar seu valor. Use ``Queue<T>`` se precisar acessar as informações na mesma ordem em que estão armazenadas na coleção. Use ``Stack<T>`` se precisar acessar as informações na ordem inversa. Use ``ConcurrentQueue<T>`` ou ``ConcurrentStack<T>`` se precisar acessar a coleção de vários threads simultaneamente.

Três operações principais podem ser realizadas em uma fila e seus elementos:

- ``Enqueue`` adiciona um elemento ao final da Fila.

- ``Dequeue`` remove o elemento mais antigo do início da Fila.

- ``Peek`` retorna o elemento mais antigo que está no início da Fila, mas não o remove.

### [Pilhas](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1?view=net-6.0)

Coleção de objetos que obedecem a regra LIFO (Last-in, First-out), ou seja, o último elemento adicionado é o primeiro elemento a ser retirado. Exemplo: pilha de livros.

```C#
Stack<string> numbers = new Stack<string>();
numbers.Push("one");
numbers.Push("two");
numbers.Push("three");
numbers.Push("four");
numbers.Push("five");

// A stack can be enumerated without disturbing its contents.
foreach( string number in numbers )
{
    Console.WriteLine(number);
}
```

Três operações principais podem ser realizadas em uma Pilha e seus elementos:

- ``Push`` insere um elemento no topo da Pilha.
- ``Pop`` remove um elemento do topo da Pilha.
- ``Peek`` retorna um elemento que está no topo da Pilha, mas não o remove da Pilha.

### [Dicionários](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2?view=net-6.0)

A classe genérica ``Dictionary<TKey, TValue>`` fornece um mapeamento de um conjunto de chaves para um conjunto de valores. Cada adição ao dicionário consiste em um valor e sua chave associada. Recuperar um valor usando sua chave é muito rápido, próximo a **O(1)**, porque a classe ``Dictionary<TKey, TValue>`` é implementada como uma tabela hash.

```C#
Dictionary<string, string> openWith = new Dictionary<string, string>();

// Add some elements to the dictionary. There are no
// duplicate keys, but some of the values are duplicates.
openWith.Add("txt", "notepad.exe");
openWith.Add("bmp", "paint.exe");
openWith.Add("dib", "paint.exe");
openWith.Add("rtf", "wordpad.exe");

// The Add method throws an exception if the new key is
// already in the dictionary.
try
{
    openWith.Add("txt", "winword.exe");
}
catch (ArgumentException)
{
    Console.WriteLine("An element with Key = \"txt\" already exists.");
}

// When you use foreach to enumerate dictionary elements,
// the elements are retrieved as KeyValuePair objects.
foreach( KeyValuePair<string, string> kvp in openWith )
{
    Console.WriteLine("Key = {0}, Value = {1}", kvp.Key, kvp.Value);
}
```

## Operações [LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)

Consulta Integrada à Linguagem (LINQ) é o nome de um conjunto de tecnologias baseadas na integração de recursos de consulta diretamente na linguagem C #. LINQ pode ser usado para acessar coleções. As consultas LINQ fornecem recursos de filtragem, ordenação e agrupamento.

```C#
int[] numbers = { 5, 10, 8, 3, 6, 12};

//Query syntax:
IEnumerable<int> numQuery1 =
    from num in numbers
    where num % 2 == 0
    orderby num
    select num;

//Method syntax:
IEnumerable<int> numQuery2 = numbers.Where(num => num % 2 == 0).OrderBy(n => n);

foreach (int i in numQuery1)
{
    Console.Write(i + " ");
}
Console.WriteLine(System.Environment.NewLine);
foreach (int i in numQuery2)
{
    Console.Write(i + " ");
}

/*
    Output:
    6 8 10 12
    6 8 10 12
 */
```

## Referências

[Documentação Microsoft - Array Class](https://docs.microsoft.com/en-us/dotnet/api/system.array?view=net-6.0)<br>
[Wikipédia - Algoritmos de Ordenação](https://en.wikipedia.org/wiki/Sorting_algorithm)<br>