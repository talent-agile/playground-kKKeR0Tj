# Regular Expressions - Groups

When building a regular expression pattern, you can specify groups that will match one value between multiple possible values. This is done using the parenthesis : `(banana|ananas|apple)`.
This example will match any text containing `banana`, `ananas` or `apple`.

```C# runnable
// { autofold
using System;
using System.Text.RegularExpressions;

class Example 
{
    static void Main()
    {
// }
        // This pattern will match any string containing banana, ananas or apple
        var regularExpression = new Regex("(banana|ananas|apple)");

        Console.WriteLine($"IsMatch 'I love fruits, my favorite is ananas': {regularExpression.IsMatch("I love fruits, my favorite is ananas")}");
        Console.WriteLine($"IsMatch 'I ate an apple this morning': {regularExpression.IsMatch("I ate an apple this morning")}");
        Console.WriteLine($"IsMatch 'My favorite ice cream flavor is strawberry': {regularExpression.IsMatch("My favorite ice cream flavor is strawberry")}");
// { autofold 
    }
}
// }
```