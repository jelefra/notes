# Hello World

```
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main()
        {
            Console.WriteLine("My name is Jeremy.");
        }
    }
}
```

```
Console.WriteLine("How old are you?");
string input = Console.ReadLine();
Console.WriteLine($"You are {input} years old!");
```

```
// One-line comment
```

```
/*
Three-line comment
*/
```

**ASP.NET** and **.NET Core** are two C#-compatible _frameworks_.

.NET generally refers to the family of programs and commands that let you make applications with C#.

The command `Console.WriteLine()` prints text to the console.

The command `Console.ReadLine()` captures user input in the console.

# Data Types and Variables

C# is _strongly-typed_, so it requires us to specify the data types that we're using.

It is also _statically-typed_, which means it will check that we used the correct types before the program even runs.

Data types:
- `int` - whole numbers, like: 1, -56, 948
- `double` - decimal numbers, like: 239.43909, -660.01
- `char` - single characters, like: "a", "&", "£"
- `string` - string of characters, like: "dog", "hello world"
- `bool` - boolean values, like: true or false

```
// declare an integer
int myAge;
myAge = 32;
```

```
// declare a string
string countryName = "Netherlands";
```

There are a few words that you can't use as variables. These are known as _reserved keywords_.

See https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords

Because variables have to be strictly typed, there may be some circumstances where we want to change the type of data a variable is storing. This strategy is known as _data type conversion_.

```
double myDouble = 3.2;
```

```
// Attempt to round myDouble to the nearest whole number
int myInt = myDouble;
int myInt = 3;

// Turn it into a decimal
double MyDouble = myInt;
```

C# checks to make sure that when we convert data types from one to another that we're not losing any data, because that could cause problems in our code.

Because of that, there are a couple different ways to do data type conversion:

* _implicit conversion_: happens automatically if no data will be lost in the conversion. That's why it's possible to convert an `int` (which can hold less data) to a `double` (which can hold more), but not the other way around.

* _explicit conversion_: requires a `cast` operator to convert a data type into another one. So if we do want to convert a `double` to an `int`, we could use the operator `(int)`.

```
double myDouble = 3.2;

// Round myDouble to the nearest whole number
int myInt = (int)myDouble;
```

It's also possible to convert data types using built-in methods. For most data types, there is a `Convert.To...` method, like `Convert.ToString` and `Convert.ToDouble`.

One example of when we have to use conversions is when we ask a user to input a numerical value. Even if that value is an `integer` or a `decimal`, `Console.ReadLine()` will always return a `string`.

```
// Ask user for fave number
Console.Write("Enter your favourite number!: ");

// Turn that answer into an int
// Does not work
int faveNumber = (int)Console.ReadLine();

// Works
int faveNumber = Convert.ToInt32(Console.ReadLine());
```

```
bool isTrue = true;
string boolToString = isTrue.ToString();
Console.WriteLine(boolToString); // "True"
string isString = "I am a string";
```

## Working with Numbers

A `double` is usually the best choice of the three because it is more precise than a `float`, but faster to process than a `decimal`. However, make sure to use a `decimal` for financial applications, since it is the most precise.

```
decimal variableName = 489872.76m;
Console.WriteLine(5 / 3); // prints 1
Console.WriteLine(5 / 3.0); // prints 1.66667
```

C# follows the _order of operations_: 1 + 2 * 3 = 7

`Math.Abs()` - will find the absolute value of a number.

`Math.Sqrt()` - will find the square root of a number.

`Math.Floor()` - will round the given double or decimal down to the nearest whole number.

`Math.Min()` - returns the smaller of two numbers.

`Math.Pow()` - Returns a specified number raised to the specified power.

`Math.Max()` - Returns the larger of two specified numbers.

`Math.Ceiling()` - Returns the smallest integral value greater than or equal to the specified number.

## Working with Text

_String concatenation_ is when we combine strings using the addition symbol (`+`), literally adding one string to another.

```
string yourFaveMusician = "David Bowie";
string myFaveMusician = "Solange";
Console.WriteLine("Your favourite musician is " + yourFaveMusician + " and mine is " + myFaveMusician + ".");
```

_String Interpolation_

```
string yourFaveMusician = "David Bowie";
string myFaveMusician = "Solange";
Console.WriteLine($"Your favourite musician is {yourFaveMusician} and mine is {myFaveMusician}.")
```

```
string userTweet = Console.ReadLine();
userTweet.Length; // returns the length of the tweet
```

```
string word = "radio";
word.IndexOf("a"); // returns 1
```

```
string plantName = "Cactaceae, Cactus";
int charPosition = plantName.IndexOf("Cactus"); // returns 11
string commonName = plantName.Substring(charPosition); // returns Cactus
```

_Bracket Notation_

```
string plantName = "Cactaceae, Cactus";
int charPosition = plantName.IndexOf("u"); // returns 15
char u = plantName[charPosition]; // returns u
```

### Manipulate Strings

Using these methods on a string **doesn't change the string itself**, but creates an entirely new one.

```
string shouting = "I'm not shouting, you're shouting".ToUpper();
Console.WriteLine(shouting);
// prints I'M NOT SHOUTING, YOU'RE SHOUTING.
```

```
cameraDirections = cameraDirections.ToUpper();
```

Notice the difference between `Console.Write()` and `Console.WriteLine()`. The latter creates a newline, but the former doesn't.

```
Console.WriteLine("Amount to convert? ");
string totalAs String = Console.ReadLine();
double totalAs Double = Convert.ToDouble(totalAsString);
```

# Logic and Conditionals

## Understanding logic in C#

_Comparison operators_:
- Equals `==`
- Inequality operator `!=`
- Less than `<`
- Greater than `>`
- Less than or equal to `<=`
- Greater than or equal to `>=`

_Logical operators_:
- AND `&&`
- OR `||`
- NOT `!`

## Conditional Statements

```
string color = "blue";

if (color == "blue")
{
    // this code block will execute only if the value of color is
    // equivalent to "blue"
    Console.WriteLine("color is blue");
}
else if (color == "red")
{
    // this code block will execute if the value of color is
    // equivalent to "red"
    Console.WriteLine("color is NOT blue");
    }
else // this is optional
{
    // this code block will execute if the value of color is
    // NOT equivalent to "blue" OR "red"
    Console.WriteLine("color is NOT blue OR red");
}
```

```
string color;
string color = "blue";

switch (color)
{
    case "blue":
    // execute if the value of color is "blue"
    Console.WriteLine("color is blue");
    break;

    case "red":
    // execute if the value of color is "red"
    Console.WriteLine("color is red");
    break;

    case "green":
    // execute if the value of color is "green"
    Console.WriteLine("color is green");
    break;
    
    default:
    // execute if none of the above conditions are met
    break;
}
```

Ternary Operators

```
string color = "blue";
string result = (color == "blue") ? "blue" : "NOT blue";
Console.WriteLine(result);
```

# Methods

## Method Calls and Input

We activate a method's behaviour by calling it.

Some methods accept inputs called arguments. `Console.WriteLine()` accepts one string argument.

The basic structure of a method definition looks like this:

```
static void YourMethodName()
{

}
```

In C#, it's convention to use _PascalCase_ to name your method.

While we are defining our method, we don't know the actual argument values that will be used when calling the method. But we do know the expected data type and how it will be used. We can use this information to define a _parameter_, which sort of works like a variable within a method. Imagine it as a placeholder for the actual _argument_ value.

```
static void YourMethodName(string identity)
{
    Console.WriteLine(identity);
}
```

The `YourMethodName()` method now has one _parameter_ named `identity` of type `string`.

When you call your method, the values to be used for each parameter are called _arguments_. In this case `"Yoda"` and `900` are arguments for the `identity` and `age` _parameters_.

```
YourMethodName("Yoda", 900);
```

One thing to watch for with parameters: they can only be used inside their method!

```
static void YourMethodName(string message)
{
    Console.WriteLine(message);
}

Console.WriteLine(message); // causes an error!
```

When talking to other developers about this type of issue, you might hear the term _scope_.

### Optional Parameters

```
static void Main(string[] args)
{
    YourMethodName("I'm hungry", "!"); // prints "I'm hungry!"
    YourMethodName("I'm hungry"); // prints "I'm hungry."
}

static void YourMethodName(string message, string punctuation = ".")
{
    Console.WriteLine(message + punctuation);
}
```

```
static void YourMethodName(int a = 0, int b = 0, int c = 0, int d = 0, int e = 0) {...}

YourMethodName(d: 4, b: 1, a: 2);
```

You can also mix them with _positional arguments_, but they MUST come before named arguments:

```
YourMethodName(2, 1, d: 4) // a is 2, b is 1, d is 4

YourMethodName(d: 4, 2, 1) // Error!
```

Say you want to use `Math.Round()`, a built-in method. You go to the Microsoft documentation to learn how to use it, and find at least 8 different versions! They all have the same name: `Math.Round()`.

What's happening here is called _method overloading_, and each "version" is called an _overload_.

```
// Math.Round(Double, Int32) rounds the double to the int's number of decimal points
Math.Round(3.14159, 2); // returns 3.14

// Math.Round(Double) rounds the double to the nearest integer.
Math.Round(3.14159); // returns 3
```

In C#, when we say that the methods are "different", we are really talking about their method _signatures_, which is the **method's name and parameter types in order**.

**Values passed to a method are called _arguments_. When defined in the method, they are _parameters_.**

## Method Output

```
static string Yell(string phrase)
{
    return phrase.ToUpper();
}

public static void Main()
{
    string output = Yell("who's there?");
    Console.WriteLine(output); // Prints WHO'S THERE?
}
```

Here's a more generic definition: the keyword `return` tells the computer to exit the method and return a value to wherever the method was called.

```
error CS1520: Method must have a return type
```

```
error CS0161: [MethodName]: not all code paths return a value
```

```
error CS0029: Cannot implicitly convert type 'string' to 'int'
```

The `Int32.TryParse()` method tries to parse its input as an integer. If it can, it returns `true` and sets a specific variable to the new value. If it cannot it returns `false` and sets a specific variable to `null`. This is what the method's signature looks like:

```
public static bool TryParse(string s, out int result);
int number;
bool success = Int32.TryParse("10602", out number);
// number is 10602 and success is true
```

```
int number2;
bool success2 = Int32.TryParse(" !!! ", out number2);
// number2 is null and success2 is false
```

```
bool success = Int32.TryParse("10602", out int number);
```

We can use `out` parameters in our own methods as well. In this example, `Yell()` converts `phrase` to uppercase and sets a boolean variable to `true`:

```
static string Yell(string phrase, out bool wasYellCalled)
{
    wasYellCalled = true;
    return phrase.ToUpper();
}
```

```
error CS0177: The out parameter 'success' must be assigned to before control leaves the current method
```

```
error CS1620: Argument 2 must be passed with the 'out' keyword
```

Every method has a return type, designated in its method signature.

If a method returns no type, its return type is `void`.

`out` parameters can be used to **return multiple values from a method**.

### Alternate Expressions

In C# there are other ways to define a method, which can save us effort in typing and make our code easier to read. They're called _expression-bodied definitions_ and _lambda expressions_.

_Expression-bodied definitions_ are the first "shortcut" for writing methods. They're great for writing one-line methods, like this one:

```
bool IsEven(int num)
{
    return num % 2 == 0;
}
```

```
bool isEven(int num) => num % 2 == 0;
```

`=>` is called a _fat arrow_.

```
void Shout(string x) => Console.WriteLine(x.ToUpper());
```

This type of definition can only be used when a method contains one expression. This helps us remember the name: **_expression-bodied definitions_ are method definitions with one expression**.

```
int[] numbers = {1, 3, 5, 6, 7, 8};

public static bool IsEven(int num)
{
    return num % 2 == 0;
}

bool hasEvenNumber = Array.Exists(numbers, IsEven);
```

The next shortcut, _lambda expressions_, are great for situations when you need to pass a method as an argument.

```
bool hasEvenNumber = Array.Exists(numbers, (int num) => num % 2 == 0 );
```

What makes a lambda expression unique is that it is an anonymous method: it has no name.

Lambda expressions with more than one expression use curly braces and semicolon:

```
(input-parameters) => { statement; }
```

```
bool hasBigDozen = Array.Exists(numbers, (int num) => {
    bool isDozenMultiple = num % 12 == 0;
    bool greaterThan20 = num > 20;
    return isDozenMultiple && greaterThan20;
});
```

Shorter Lambda Expressions

- We can remove the parameter type if can be inferred
- We can remove the parentheses if there is one parameter

```
bool hasEvenNumbers = Array.Exists(numbers, num => num % 2 == 0 );
```

# Arrays and Loops

## Arrays

Data structures are formats designed to store larger amounts of information in an organised fashion.

An array is one very basic data structure.

What makes arrays special is that they order our data in a specific, linear sequence.

You're already familiar with strings - strings are arrays of characters.

In C#, arrays are a collection of values that all share the same data type.

```
// These arrays store ints, strings, and doubles, respectively
int[] x;
string[] s;
double[] d;
```

Like a variable, an array can be defined and initialized at the same time, by specifying the values we want to store in it:

```
int[] plantHeights = { 3, 4, 6 };
int[] plantHeights = new int[] { 3, 4, 6 };
```

The `new` keyword signifies that we are instantiating a new array from the array class.

**If you decide to define an array and then initialize it later (rather than in one line like above) you must use the `new` keyword:**

```
// Initial declaration
int[] plantHeights;

// This works
plantHeights = new int[] { 3, 4, 6 };

// This will cause an error
// plantHeights = { 3, 4, 6 };
```

```
int[] plantHeights = { 3, 4, 6 };

// arrayLength will be 3
int arrayLength = plantHeights.Length
```

Each value has a specific position in the array, which is known as its _index_.

```
// plantHeights will be equal to [0, 0, 0]
int[] plantHeights = new int[3];

// plantHeights will now be [0, 0, 8]
plantHeights[2] = 8;
```

When we create the array with a known length but no known values, the array stores a default type value (`0` for `int`, `null` for `string`).

We can also edit the values of pre-existing arrays. Again, **we can't add to the length of an existing array**, but we can swap out values:

```
int[] plantHeights = { 3, 4, 6 };

// plantHeights will be [3, 5, 6]

plantHeights[1] = 5;
```

* `Array.Sort()`

`Sort()` takes an array as a parameter and edits the array so its values are sorted.

If it is an array of integer values, it will sort them into ascending values (lowest to highest).

If it's an array of string values, they would be sorted alphabetically.

* `Array.IndexOf()`

`IndexOf()` typically takes two parameters: the first is the array and the second is the value whose index we're locating.

**If it cannot find the value, it returns the lower bound of the array, minus 1 (since most arrays start at 0, it's usually -1).**

* `Array.Find()`

Searches a one-dimensional array for a specific value or set of values that match a certain condition and returns the first occurrence in the array.

```
int[] plantHeights = { 3, 6, 4, 1, 6, 8 };

// Find the first occurrence of a plant height that is greater than 5 inches
int firstHeight = Array.Find(plantHeights, height => height > 5);
```

`Find()` takes two parameters: the first is the array and the second is a predicate that defines what we're looking for.

A _predicate_ is a method that **takes one input and outputs a boolean**.

* `Array.Copy()` copies a range of elements from one array to a second array. It takes three parameters: the name of the array to be copied, the new array, and the length of the array elements.

```
string[] players = { "Emily", "Kyle", "Todd", "Rachel", "Grayson" };

// This creates a new array with default values
string[] playersCopy = new string[5];

// This will populate the playersCopy array with { "Grayson", "Rachel", "Todd", "Kyle", "Emily" }
Array.Copy(players, playersCopy, 5);
```

* `Array.Reverse()` will switch the order of elements in an entire array. It can also reverse them in a portion of an array, if the overload is used:

```
string[] players = { "Emily", "Kyle", "Todd", "Rachel", "Grayson" };

// This will return { "Grayson", "Rachel", "Todd", "Kyle", "Emily" }
Array.Reverse(players);
```

* `Array.Clear()` sets a range of elements in an array to the default value. It takes three parameters: the name of the array, the starting index of the range to clear, and the number of elements to clear.

To clear an entire array, set the index to 0 (if it is zero-indexed) and then pass in the length of the array for the third parameter.

```
string[] players = { "Emily", "Kyle", "Todd", "Rachel", "Grayson" };

// This will return { 0, 0, 0, 0, 0 }
Array.Clear(players, 0, players.Length);
```

## Loops

A loops is a structure that we can use to repeat instructions until a certain condition is met. That condition could be a change in state ("keep playing music until 10pm"), an end of a list ("say each name out loud"), or a number ("knock three times").

## While Loop

```
while (condition)
{
    statement;
}
```

### Do...While Loop

```
do
{
    statement;
} while (condition);
```

### For Loop

```
for (initialisation; stopping condition; iteration statement)
{
    statement;
}
```

```
for (int i = 0; i < 10; i++)
{
    DisplayFlag();
}
```

### For Each Loop

```
foreach (type element in sequence)
{
    statement;
}
```

```
string[] melody = { "a", "b", "c", "c", "b" };

foreach (string note in melody)
{
    PlayMusic(note);
}
```

The sequence we used was an array, but we can use other similar data structure. The umbrella term for those is _collection_, so we can also call foreach loops _collection loops_.

- while loops are good when you know your stopping condition, but not when you know how many times you want a program to loop or if you have a specific collection to loop through.
- do...while loops are only necessary if you definitely want something to run once, but then stop if a condition is met.
- for loops are best if you want something to run a specific number of times, rather than given a certain condition.
- foreach loops are the best way to loop over an array, or any other collection.

At any point within a loop block, you can end it by using the `break` keyword.

```
while (playerIsAlive)
{
    // this code will keep running
    if (playerIsAlive == false)
    {
        // eventually if this stopping condition is true,
        // it will break out of the while loop
        break;
    }
}

// rest of the program will continue
```

```
int bats = 10;
for (int i = 0; i <= 10; i++)
{
    if (i < 9)
    {
        continue;
    }
    // this will be skipped until i is no longer less than 9
    Console.WriteLine(i);
}
```

```
class MainClass {
    public static void Main (string[] args) {
        UnlockDoor();
        // after it hits the return statement, it will move on to this method
        PickUpSword();
    }

    static bool UnlockDoor()
    {
        bool doorIsLocked = true;
        // this code will keep running
        while (doorIsLocked)
        {
            bool keyFound = TryKey();
            // eventually if this stopping condition is true,
            // it will break out of the while loop
            if (keyFound)
            {
                // this return statement will break out of the entire method
                return true;
            }
        }
        return false;
    }
}
```

You should only use `return` if you need to exit a method, because it will break out of all loops.

- A loop is a structure in programming where the **instructions are written once, but a computer can execute them multiple times**
- Each execution of those instructions is called an _iteration_
- while loops repeat **until a condition changes**
- do...while loops **execute once, and then repeat until a condition changes**
- for loops **repeat for a specified number of times**
- foreach loops **repeat for each item in a collection**
- _jump statements_, like `break`, `continue`, and `return` are used to **add additional control flow to loops**

convert strings to arrays of characters with `ToCharArray()`
```
string msgString = "brutus";
char[] msgArray = msgString.ToCharArray();
char[] msgArray = new char[] {'b', 'r', 'u', 't', 'u', 's'};
string msgString = String.Join("", msgArray);
```

# Classes and Objects

## Basic Classes and Objects

We can define our own custom `Forest` data type and use it like any other data type in our program. This process of bundling related data and methods into a type is called _encapsulation_, and it makes code easier to organise and reuse.

In C#, **a custom data type** is defined with a class, and each _instance_ of this type is an _object_.

```
class Forest {

}

Forest f = new Forest();
```

The process of creating an instance is called _instantiation_.

We need to associate different pieces of data, like a size and name, to each Forest object. In C#, these pieces of data are called _fields_.

Create fields like this:

```
class Forest {
    public string name;
    public int trees;
}
```

It is common practice to name fields with lowercase (`name` instead of `Name`). This makes fields easy to recognise later on.

We need **a way to define what values are valid and disallow those that are not**. C# provides a tool for that: _properties_.

A property is made up of two methods:
- a `get()` method, or getter: called when the property is accessed
- a `set()` method, or setter: called when the property is assigned a value

```
public int area;
public int Area
{
    get { return area; }
    set { area = value; }
}
```

The set() method above uses the keyword `value`, which represents the value we assign to the property.

With validation:

```
public int Area
{
    get { return area; }
    set
    {
        if (value < 0) { area = 0; }
        else { area = value; }
    }
}
```

The basic getter and setter pattern is so common that there is a short-hand called an _automatic property_.

```
public string size;
public string Size
{
    get { return size; }
    set { size = value; }
}

public string Size
    { get; set; }
```

In this form, you don't have to write out the `get()` and `set()` methods, and you don't have to define a `size` field at all! **A hidden field is defined in the background for us.** All we have to worry about is the `Size` property.

```
f.Age = 32; // using property
f.age = -1; // using field
```

The second line avoids the property's validation by directly accessing the field. We can fix this by using the _access modifiers_ `public` and `private`.

- `public` — a public member can be accessed by any class
- `private` — a private member can only be accessed by code in the same class

For example, since a class's properties define how other programs get and set its fields, **it's good practice to make fields private and properties public**.

C# encourages encapsulation by defaulting class members to private and classes to public.

don't include a set():

```
public string Area
{
    get { return area; }
}
```

make set() private:
```
public int Area
{
    get { return area; }
    private set { area = value; }
}
```

The third type of member in classes is _methods_.

This code defines a method `IncreaseArea()` that changes the value of the Area property:

```
class Forest {
    public int Area
    { /* property body omitted */ }
    public int IncreaseArea(int growth)
    {
        Area = Area + growth;
        return Area;
    }
}
```

In each of the examples so far, we created a new `Forest` object and set the property values one by one. It would be nice if we could write **a method that runs every time an object is created to set those values at once**.

C# has a special type of method, called a _constructor_, that does just that.

It looks like a method, but there is no return type listed and the method name is the name of its enclosing class:

```
class Forest
{
    public Forest()
    {
    }
}
```

We can add code in the constructor to set `values` to `fields`:

```
class Forest
{
    public int Area;
    public Forest(int area)
    {
        Area = area;
    }
}
```

This constructor method is used whenever we instantiate an object with the new keyword:

```
// Constructor is called here
Forest f = new Forest(400);
```

If no constructor is defined in a class, one is automatically created for us. It takes no parameters, so it's called a parameterless constructor. That's why we have been able to instantiate new objects without errors:

```
Forest f = new Forest();

class Forest
{
    public int Area
    { /* property omitted */ }
    public Forest(int area)
    {
        Area = area;
    }
}
```

The parameter for the constructor area looks a lot like the old _field_ `area` and the new _property_ `Area`. It's good to be explicit when writing code so that there is no room for misinterpretation. We can refer to **the current instance of a class** with the `this` keyword.

```
class Forest
{
    public int Area
    { /* property omitted */ }
    public Forest(int area)
    {
        this.Area = area;
    }
}
```

`this.Area = area` means "when this constructor is used to make a new instance, use the argument `area` to set the value of this new instance's `Area` _field_".

Just like other methods, constructors can be overloaded. For example, we may want to define an additional constructor that takes one argument:

```
public Forest(int area, string country)
{
    this.Area = area;
    this.Country = country;
}

public Forest(int area)
{
    this.Area = area;
    this.Country = "Unknown";
}
```

Now you can create a Forest instance in two ways:

```
Forest f = new Forest(800, "Belgium");
Forest f2 = new Forest(400);
```

Solve duplication of code in one of two ways:

1:

```
public Forest(int area, string country = "Unknown")
{
    this.Area = area;
    this.Country = country;
}
```

2:

Use `this()`, which refers to another constructor in the same class. This is useful for old C# programs (before 4.0) and when your second constructor has additional functionality. This example has an additional functionality of announcing the default value.

```
public Forest(int area, string country)
{
    this.Area = area;
    this.Country = country;
}

public Forest(int area) : this(area, "Unknown")
{
    Console.WriteLine("Country property not specified. Value defaulted to 'Unknown'.");
}
```

Remember that `this.Area` refers to the current instance of a class. When we use `this()` like a method, it refers to another constructor in the current class. In this example, the second constructor calls `this()` — which refers to the first `Forest()` constructor — AND it prints information to the console.

When someone asks you, "How do I make a custom data type in C#?" you can talk all about it! In this lesson, you learned how to:

- Define a class
- Instantiate an object using new
- Define fields, the pieces of data for each class
- Define properties, the spokespeople for each field
- Define automatic properties, the shorthand for making properties
- Define methods, the actions a class can take
- Define constructors, the special methods called when a class is instantiated
- Overload constructors and reuse code with this
- Control access to class members using public and private

## Static Members

What if we needed to do something related to the type itself, not instances of that type? For example, where do we store the count of all `Forest` objects, or an explanation of forests in general?

These facts and behaviours should be **associated with the class itself**! We call these types of members `static`.

To make a `static` _field_ and _property_, just add `static` after the _access modifier_ (`public` or `private`).

```
class Forest
{
    private static string definition;
    public static string Definition
    {
        get { return definition; }
        set { definition = value; }
    }
}
```

Remember that `static` means "associated with the class, not an instance". Thus any static member is accessed from the class, not an instance:

```
static void Main(string[] args)
{
    Console.WriteLine(Forest.Definition);
}
```

A static method **can only access other static members**. It cannot access instance members.

### Static Constructors

An _instance constructor_ is run before an instance is used, and a _static constructor_ is run once before a class is used.

```
class Forest
{
    static Forest()
    { /* ... */ }
}
```

### Static Classes

A static class cannot be instantiated, so you only want to do this if you are making a utility or library, like `Math` or `Console`.

These two common classes are static because they are just tools — they don't need specific instances and they don't store new information.

Now when you see something like:

```
Math.Min(34, 54);
```
```
Console.WriteLine("yeehaw!");
```

You know that these are two static classes calling two static methods.

### Main

```
class Program
{
    public static void Main (string[] args)
    {
    }
}
```

- `Main()` is a method of the `Program` class.
- `public` — The method can be called outside the Program class.
- `static` — The method is called from the class name: `Program.Main()`.
- `void` — The method returns nothing.
- `string[] args` — The method has one parameter named `args`, which is an array of strings.

We can include arguments on the command line, like `dotnet run arg1 arg2 arg3` that will be converted into an array as the args parameter.

- In general, `static` means **"associated with the class, not an instance"**.
- A static member is always **accessed by the class name**, rather than the instance name, like `Forest.Area`.
- A static method **cannot access non-static members**.
- A static constructor is **run once per type**, not per instance. It is **invoked before the type is instantiated or a static member is accessed**.
- Either of these would trigger the static constructor of `Forest`:

```
public static void Main() {
    Forest f = new Forest();
}
```

or

```
public static void Main() {
    Forest.Define();
}
```

- A static class **cannot be instantiated**. Its members are accessed by the class name, like `Math.PI`.
