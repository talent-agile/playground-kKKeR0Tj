# Strings and Encoding

## Basics

`String` is a type from the `System` namespace that is used for most of text related operations.

The `String` type has some specificities compared to other types:

* It is a reference type
* It is immutable, meaning that you cannot change the value of a `String`
* It behaves like a value type


## Encodings

`Encoding` is used to specify:
* How text is stored in memory
* How text is displayed on screen

The `Encoding` type offers multiple common encodings:
* Default **(avoid using this one)**
* ASCII
* Unicode
* UTF7
* UTF8
* UTF32
 
Text in `String` instances is stored using Unicode 16.
You can include specific Unicode characters in a `String` using the syntax `\u03a0` (here it is the pi character for exemple).

```C# runnable
// { autofold 
using System;
using System.Text;

class Example 
{
    static void Main() 
    {
// }
        string unicodeString = "Maths use \u03a0 (Pi) for calculations";

        // You can convert a string into a byte array
        byte[] unicodeBytes = Encoding.Unicode.GetBytes(unicodeString);
        byte[] asciiBytes = Encoding.ASCII.GetBytes(unicodeString);

        // You can convert a byte array into a char array
        char[] asciiChars = Encoding.ASCII.GetChars(asciiBytes);
        string asciiString = new string(asciiChars);

        // The resulting string is different due to the unsupported character for ASCII encoding
        Console.WriteLine($"Unicode string: {unicodeString}");
        Console.WriteLine($"ASCII string: {asciiString}");
// { autofold   
    }   
}
// }
```

## Building `Strings`

As we saw before, `String` is immutable, which implies that every time you want to modify a `String`, a new instance will be created.
If you have an important number of modifications to do, this can cause a big memory consumption and pressure on the memory.

In order to avoid this scenario, the .Net Framework propose the `StringBuilder`class, which is designed for handling such scenarios.

```C# runnable
// { autofold
using System;

class Hello 
{
    static void Main() 
    {
// }

Console.WriteLine("Hello World!");

// { autofold
    }
}
// }
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced C# template](https://tech.io/select-repo/386)
