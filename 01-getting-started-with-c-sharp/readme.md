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

## Variable name rules and conventions

Here's a few important considerations about variable names:

- Variable names can contain alphanumeric characters and the underscore character. Special characters like the hash symbol # (also known as the number symbol or pound symbol) or dollar symbol $ are not allowed.
- Variable names must begin with an alphabetical letter or an underscore, not a number.
- Variable names are case-sensitive, meaning that string Value; and string value; are two different variables.
- Variable names must not be a C# keyword. For example, you cannot use the following variable declarations: decimal decimal; or string string;.
  
Here are some coding conventions for variables:

- Variable names should use camel case, which is a style of writing that uses a lower-case letter at the beginning of the first word and an upper-case letter at the beginning of each subsequent word. For example, string thisIsCamelCase;.
- Variable names should begin with an alphabetical letter. Developers use the underscore for a special purpose, so try to not use that for now.
- Variable names should be descriptive and meaningful in your app. Choose a name for your variable that represents the kind of data it will hold.
- Variable names should be one or more entire words appended together. Don't use contractions or abbreviations because the name of the variable (and therefore, its purpose) may be unclear to others who are reading your code.
- Variable names shouldn't include the data type of the variable. You might see some advice to use a style like string strValue;. That advice is no longer current.

**NB**: you can reassign a variable, but you cannot change it's type: 

```csharp
string firstName;
firstName = "Bob";
Console.WriteLine(firstName);
firstName = "Liem";
Console.WriteLine(firstName);
firstName = "Isabella";
Console.WriteLine(firstName);
firstName = "Yasmin";
Console.WriteLine(firstName);
```

To avoid the possibility of an unassigned local variable, it is recommended that you set the value as soon as possible after you declare it.

```csharp
string firstName; 
firstName = "David"; 

// alternatively
string anotherFirstName = "Xiao"; // can be set at time of initialisation

Console.WriteLine(firstName + " and " + anotherFirstName);
```

The C# compiler works behind the scenes to assist you as you write your code. It can infer your variable's data type by its initialized value.

```csharp
var message = "Hello world!";
```

The var keyword tells the C# compiler that the data type is implied by the assigned value. After the type is implied, the variable acts the same as if the actual data type had been used to declare it. The var keyword is used to save on keystrokes when types are lengthy or when the type is obvious from the context.

Putting it together...

```csharp
string bobsName = "bob";
int numThree = 3;
decimal thirtyFour = 34.4M; 

Console.Write($"Hello {bobsName} you have {numThree} messages in your inbox. The temperature is {thirtyFour} celsius.");
```

---

## Some string formatting

Note that the backslashes need to be doubled up to get them to appear:

```csharp
Console.WriteLine("Hello\nWorld!");
Console.WriteLine("Hello\tWorld!");
Console.WriteLine("Hello \"World\"!");
Console.WriteLine("c:\\source\\repos");
Console.WriteLine("c:\\\\source\\\\repos");
```

An example :

```csharp
Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ... \n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t");
```

output

> Generating invoices for customer "Contoso Corp" ...
> 
> Invoice: 1021           Complete!
> Invoice: 1022           Complete!
> 
> Output Directory:

## Verbatim string literal

A verbatim string literal will keep all whitespace and characters without the need to escape the backslash. To create a verbatim string, use the `@` directive before the literal string.

```csharp
Console.WriteLine(@"    c:\source\repos    
        (this is where your code goes)");
```

## Unicode escape characters

You can also add encoded characters in literal strings using the `\u` escape sequence, then a four-character code representing some character in Unicode (UTF-16).

```csharp
// Kon'nichiwa World
Console.WriteLine("\u3053\u3093\u306B\u3061\u306F World!");
```

output: // こんにちは World!

---

**There are several caveats here. First, some consoles like the Windows Command Prompt will not display all Unicode characters. It will replace those characters with question mark characters instead. Also, the examples used here are UTF-16. Some characters require UTF-32 and therefore require a different escape sequence. This is a complicated subject, and this module is only aiming at showing you what is possible. Depending on your need, you may need to spend quite a bit of time learning and working with Unicode characters in your applications.**

---

### Format output using unicode escape characters

To complete the mock-up of the command-line tool, you'll add a phrase in Japanese that translates: "To generate Japanese invoices". Then you'll display a verbatim literal string that represents a command the user can enter. You'll also add some escape sequences for formatting.

```csharp
Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ... \n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t");
Console.Write(@"c:\invoices");

// To generate Japanese invoices:
// Nihon no seikyū-sho o seisei suru ni wa:
Console.Write("\n\n\u65e5\u672c\u306e\u8acb\u6c42\u66f8\u3092\u751f\u6210\u3059\u308b\u306b\u306f\uff1a\n\t");
// User command to run an application
Console.WriteLine(@"c:\invoices\app.exe -j");
```

output: 

```
Generating invoices for customer "Contoso Corp" ...

Invoice: 1021            Complete!
Invoice: 1022            Complete!

Output Directory:
c:\invoices

日本の請求書を生成するには：
    c:\invoices\app.exe -j
```



