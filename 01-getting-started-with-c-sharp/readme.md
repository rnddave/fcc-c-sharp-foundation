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



