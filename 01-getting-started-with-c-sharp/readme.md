# Interesting things I read from MS documentation: 

const & literal = same thing. 

> This hard-coded value can also be called a constant, or a literal value.

## In this module, you will:
- Create literal values for five basic data types
- Declare and initialize variables
- Retrieve and set values in variables
- Allow the compiler to determine the data type for your variable when initializing

#### char
- single quotes for single characters
- a double quote, tells the system, this is a string
- Both a **char** and a **string** should be used for numerics if they are not used in mathematical operations. IE for presentation only, then a char or a string is better than a numeric type 

#### int
- need to know about signed and unsigned 
- but we're not touching that stuff yet

#### float
- this uses **F**
- this is the least precise data type
- only use for fixed fractionals to avoid calculation errors

#### double
- enter a decimal, adding the **.** will tell system this is a **double**

#### decimal literal 
- To create a decimal literal, append the letter **m** after the number. In this context, the m is called a **literal suffix**. The literal suffix tells the compiler you wish to work with a value of decimal type. *You can use either a lower-case m or upper-case M as the literal suffix for a decimal.*

#### Boolean
- usual, true, false stuff

```csharp
// String 
Console.WriteLine("String = Double Quotes");
// Char
Console.WriteLine('b');
// Int (unsigned I guess)
Console.WriteLine(123);
// Float
Console.WriteLine(0.25F); 
// Double
Console.WriteLine(2.625);
// decimal literal - not susre what this is tbh
Console.WriteLine(12.39816m);
// bool
Console.WriteLine(true); // Interesting - the output is True
Console.WriteLine(false); // output has capital = False
```

---

