# Generics in C#

---
## Docs and Source
[Docs](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/generics)

---
## Explanation and Notes

Generics in C# are how you define types which do not have to be set until they are instantiated. Below is an example from the MS docs.

---
## Code Example

```csharp
// Declare the generic class.
public class GenericList<T>
{
    public void Add(T input) { }
}
class TestGenericList
{
    private class ExampleClass { }
    static void Main()
    {
        // Declare a list of type int.
        GenericList<int> list1 = new GenericList<int>();
        list1.Add(1);

        // Declare a list of type string.
        GenericList<string> list2 = new GenericList<string>();
        list2.Add("");

        // Declare a list of type ExampleClass.
        GenericList<ExampleClass> list3 = new GenericList<ExampleClass>();
        list3.Add(new ExampleClass());
    }
}
```


#C-Sharp
