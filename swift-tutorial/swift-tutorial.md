**Welcome to the Swift Tutorial!**
----------------------------------

<img width="1000" alt="image" src="https://user-images.githubusercontent.com/88003574/171659201-db627d62-eb3e-482b-93ef-847664f63238.png">

------------------------------------------------------------------------------------------------------------------------------

**Resources**
-------------

This guide is based on these tutorials:

- [Swift Tutorial Part 1: Expressions, Variables and Constants](https://www.raywenderlich.com/6338-swift-tutorial-part-1-expressions-variables-and-constants)
- [Swift Tutorial Part 2: Types and Operations](https://www.raywenderlich.com/6364-swift-tutorial-part-2-types-and-operations)
- [Swift Tutorial Part 3: Flow Control](https://www.raywenderlich.com/965-swift-tutorial-part-3-flow-control)

**Creating a Playground**
-------------------------

When you open Xcode, it will greet you with the following welcome screen:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659301-92d881d3-d9fb-4968-bb6a-b54133b865ad.png">

If you don't see this screen, it's most likely because the Show this window when Xcode launches option was unchecked. You can also open the screen by pressing Command-Shift-1. You can also click Window ▸ Welcome to Xcode from the menu bar.

From the Welcome screen, you can jump quickly into a playground by clicking on Get started with a playground. Click on that now and Xcode will present you with a choice of templates.

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659348-61eff048-fff9-4ebe-adcd-40b4329b3dfa.png">

The platform you choose simply defines which version of the template Xcode will use to create the playground. Currently, your options are iOS, macOS or tvOS. Each platform comes with its own environment set up and ready for you to begin playing around inside with code. For the purposes of this tutorial, choose whichever platform you wish. You won't be write any platform-specific code; instead, you'll learn the core principles of the Swift language.

Select the Blank template and click Next. Xcode will now ask you to name the playground and select a location to save it. The name is merely cosmetic and for your own use; when you create your playgrounds, feel free to choose names that will help you remember what they're about.

Click Create to create and save the playground. Xcode then presents you with the playground, like so:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659391-f9cf3f38-88fe-4bfc-9e33-9f874078008b.png">

New playgrounds don't start entirely empty but have some basic starter code to get you going. Don't worry --- you'll soon learn what this code means.

Playgrounds Overview

At first glance, a playground may look like a rather fancy text editor. Well, here's some news for you: It's essentially just that!

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659434-5af4a0a7-9e83-46cc-8a6d-492acadddb46.png">

The screenshot above highlights the first and most important things to know about the following:

1.  **Source editor**: This is the area in which you'll write your Swift code. It's much like a text editor such as Notepad or TextEdit. You'll notice that it uses what's known as a monospace font, which means all characters are the same width. This makes the code much easier to read and format.

2.  **Results sidebar:** This area shows the results when you execute your code. You'll learn more about how code is executed as you read through the series. The results sidebar is the main place that you'll look to confirm your code is working as expected.

3.  **Execution control**: Playgrounds execute automatically by default, meaning you can write code and immediately see the output. This control allows you to execute the playground again. Holding down the ▶︎ (Execute) button allows you to switch between automatic execution and manual execution modes.

4.  **Activity viewer**: This shows the status of the playground. In the screenshot above, it shows that the playground has finished executing and is ready to handle more code in the source editor. When the playground is executing, the viewer will indicate this with a spinner.

5.  **Panel controls**: These toggle switches show and hide three panels, one that appears on the left, one on the bottom and one on the right. The panels each display extra information that you may need to access from time to time. You'll usually keep them hidden, as they are in the screenshot. You'll learn more about each of these panels as you move through the series.

Playgrounds execute the code in the source editor from top to bottom. Every time you change the code, the playground will re-execute everything. You can also force a re-execution by clicking Editor ▸ Run Playground in the menu bar. Alternatively, you can use the execution control.

You can turn on line numbers on the left side of the source editor by clicking Xcode▸ Preferences... ▸ Text Editing ▸ Line Numbers in the menu bar. Line numbers can be very useful when you want to refer to parts of your code.

Once the playground finishes execution, Xcode updates the results sidebar to show the results of the corresponding lines in the source editor. You'll see how to interpret the results of your code as you work through the examples in this series.

Code comments, arithmetic operations, constants and variables are some of the fundamental building blocks of any language, and Swift is no different.

**Code Comments**
-----------------

Swift, like most other programming languages, allows you to document your code through the use of what are called **comments**. These allow you to write any text directly alongside your code, which is ignored by the compiler.

Single line comment:

```
// This is a comment. It is not executed.
```

Multi line comment:

```
 /* This is also a comment.
         Over many...
         many...
         many lines. */
 ```

**Printing Out**
----------------

It's also useful to see the results of what your code is doing. In Swift, you can achieve this through the use of the print command.

print will output whatever you want to the **debug area**, which is sometimes referred to as the **console**.

For example, consider the following code:

```
print("Hello, Swift Apprentice reader!")
```

This will output a nice message to the debug area, like so:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659581-4066d28e-eee6-4211-b0d8-1ea4b9fd758b.png">

You can hide or show the debug area using the downward-arrow-in-a-box button highlighted in red in the image above. You can also click **View** ▸ **Debug Area** ▸ **Show Debug Area** in the menu bar to do the same thing.

### **Simple Operations**

All operations in Swift use a symbol known as the **operator** to denote the type of operation they perform.

Consider the four arithmetic operations that you learned in your early school days: addition, subtraction, multiplication and division. For these simple operations, Swift uses the following operators:

- Add: +
- Subtract: -
- Multiply: *
- Divide: /

These operators are used like so:

```
2 + 6

10 - 2

2 * 4

24 / 3
```

Each of these lines is what is known as an **expression**. An expression has a value. In these cases, all four expressions have the same value: 8.

### **Decimal Numbers**

All of the operations above have used whole numbers, more formally known as **integers**. However, as you will know, not every number is whole.

As an example, consider the following:

```
22.0 / 7.0
```

This, you may be surprised to know, results in the number 3. This is because, if you only use integers in your expression, Swift makes the result an integer. In this case, the result is rounded down to the next integer.

You can tell Swift to use decimal numbers by changing it to the following:

```
22.0 / 7.0
```

This time, the result is 3.142857142857143, as expected.

The four operations you've seen so far are easy to understand because you've been doing them for most of your life. Swift also has more complex operations you can use, all of them standard mathematical operations --- just less common ones.

### **Order of Operations**

There are many times that it is necessary to use multiple operators to calculate a value. Here's an example of how to do this in Swift:

```
((8000 / (5 * 10)) - 32))+ (29 % 5)
```

Notice the use of parentheses, which, in Swift, serve two purposes: to make it clear to anyone reading the code --- including yourself --- what you meant, and to disambiguate.

**Naming Data**
---------------

At its simplest, computer programming is all about manipulating data. Remember, everything you see on your screen can be reduced to numbers that you send to the CPU. Sometimes, you yourself represent and work with this data as various types of numbers; other times, the data comes in more complex forms such as text, images and collections.

In your Swift code, you can give each piece of data a name that you use to refer to it later. The name carries with it an associated **type** that denotes what sort of data the name refers to, such as text, numbers or a date.

You'll learn about some of the basic types next, and you'll encounter many other types throughout the rest of this series.

### **Constants**

Take a look at this:

```
let number: Int = 10
 ```

This declares a constant called number, which is of type Int. Then, it sets the value of the constant to the number 10.

**Note**: Thinking back to operators, here's another one: The equals sign, =, is known as the **assignment operator**.

The type Int can store integers. The way you store decimal numbers is like so:

```
let pi: Double = 3.14159
```

This is similar to the Int constant, except the name and the type are different. This time, the constant is a Double, a type that can store decimals with high precision.

There's also a type called Float, short for floating point, that stores decimals with lower precision than Double. In fact, Double has about double the precision of Float, which is why it's called Double in the first place. A Float takes up less memory than a Double but, generally, memory use for numbers isn't a huge issue and you'll see Double used in most places.

Once you've declared a constant, you can't change its data. For example, consider the following code:

```
let number: Int = 10
number = 0
```

This code produces an error:

Cannot assign to value: 'number' is a 'let' constant

In Xcode, you would see the error represented this way:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659676-e83bab74-9afa-4d24-a02b-438d9f4fa043.png">

Constants are useful for values that aren't going to change. For example, if you were modeling an airplane and needed to keep track of the total number of seats available, you could use a constant.

You might even use a constant for something like a person's age. Even though their age will change with each birthday, you might only be concerned with their age at this particular instant.

### **Variables**

Often, you want to change the data behind a name. For example, if you were keeping track of your bank account balance with deposits and withdrawals, you might use a variable rather than a constant.

If your program's data never changed, then it would be a rather boring program! But, as you've seen, it's not possible to change the data behind a constant.

When you know you'll need to change some data, you should use a variable to represent that data instead of a constant. You declare a variable in a similar way, like so:

```
var variableNumber: Int = 42
```

Only the first part of the statement is different: You declare constants using let, whereas you declare variables using var.

Once you've declared a variable, you're free to change it to whatever you wish, as long as the type remains the same. For example, to change the variable declared above, you could do this:

```
variableNumber = 0
variableNumber = 1_000_000
```

To change a variable, you simply assign it a new value.

**Note**: In Swift, you can optionally use underscores to make larger numbers more human-readable. The quantity and placement of the underscores are up to you.

This is a good time to take a closer look at the results sidebar of the playground. When you type the code above into a playground, you'll see that the results sidebar on the right shows the current value of variableNumber at each line:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659741-e1b7c30b-1e6f-4dec-b2a4-3b10337f47cf.png">

The results sidebar will show a relevant result for each line if one exists. In the case of a variable or constant, the result will be the new value, whether you've just declared a constant, or if you've declared or reassigned a variable.

### **Using Meaningful Names**

Always try to choose meaningful names for your variables and constants. Good names, like good comments, can make your code easier to read.

A good name *specifically* describes what the variable or constant represents. Here are some examples of good names:

- personAge
- numberOfPeople
- gradePointAverage

Often, a bad name is simply not descriptive enough. Here are some examples of bad names:

- a
- temp
- average

The key is to ensure that you'll understand what the variable or constant refers to when you read it again later. Don't make the mistake of thinking you have an infallible memory! It's common in computer programming to look back at your own code as early as a day or two later and have forgotten what it does. Make it easier for yourself by giving your variables and constants intuitive, precise names.

Also, note how the names above are written. In Swift, it is common to **camel case**names, explained below. For variables and constants, follow these rules to properly case your names:

- Start with a lowercase letter.
- If the name is made up of multiple words, join them together and start each subsequent word with an uppercase letter.
- If one of these words is an abbreviation, write the entire abbreviation in the same case (e.g., sourceURL and urlDescription).

**Types**

Sometimes, you'll have data in one format and need to convert it to another. The naïve way to attempt this would be like so:

```
var integer: Int = 100
var decimal: Double = 12.5
integer = decimal
```

Swift will complain if you try to do this and spit out an error on the third line:

Cannot assign value of type 'Double' to type 'Int'

Some programming languages aren't as strict and will perform conversions like this automatically. Experience shows this kind of automatic conversion is the source of software bugs, and it often hurts performance. Swift prevents you from assigning a value of one type to another and this avoids these issues.

Remember, computers rely on programmers to tell them what to do. In Swift, that includes being explicit about type conversions. If you want the conversion to happen, you have to say so!

Instead of simply assigning, you need to explicitly write that you want to convert the type. You do it like so:

```
var integer: Int = 100
var decimal: Double = 12.5
integer = Int(decimal)
```

The assignment on the third line now tells Swift, unequivocally, that you want to convert from the original type, Double, to the new type, Int.

**Note**: In this case, assigning the decimal value to the integer results in a loss of precision: The integer variable ends up with the value 12 instead of 12.5. This is why it's important to be explicit. Swift wants to make sure that you know what you're doing and that you may end up losing data by performing the type conversion.

### **Operators With Mixed Types**

So far, you've only seen operators acting independently on integers or doubles. But what if you have an integer that you want to multiply by a double?

You might think you could do it like this:

```
let hourlyRate: Double = 19.5
let hoursWorked: Int = 10
let totalCost: Double = hourlyRate * hoursWorked
```

If you try that, you'll get an error on the final line:

Binary operator '*' cannot be applied to operands of type 'Double' and 'Int'

This is because, in Swift, you can't apply the * operator to mixed types. This rule also applies to the other arithmetic operators. It may seem surprising at first, but Swift is being rather helpful.

Swift forces you to be explicit about what you mean when you want an Intmultiplied by a Double, because the result can be only *one* type. Do you want the result to be an Int, converting the Double to an Int before performing the multiplication? Or do you want the result to be a Double, converting the Int to a Double before performing the multiplication?

In this example, you want the result to be a Double. You don't want an Int, because, in that case, Swift would convert the hourlyRate constant into an Int to perform the multiplication, rounding it down to 19 and losing the precision of the Double.

You need to tell Swift you want it to consider the hoursWorked constant to be a Double, like so:

```
let hourlyRate: Double = 19.5
let hoursWorked: Int = 10
let totalCost: Double = hourlyRate * Double(hoursWorked)
```

Now, each of the operands will be a Double when Swift multiplies them, so totalCost is a Double as well.

### **Type Inference**

Up to this point, each time you've seen a variable or constant declared, it's been accompanied by an associated type, like this:

```
let integer: Int = 42
let double: Double = 3.14159
```

You may be asking yourself: "Why must I write the : Int and : Double, when the right-hand side of the assignment *is already* an Int or a Double?" It's redundant, to be sure; you can see this without too much work.

It turns out that the Swift compiler can deduce this as well. It doesn't need you to tell it the type all the time --- it can figure it out on its own. This is done through a process called **type inference**. Not all programming languages have this, but Swift does, and it's a key component of Swift's power as a language.

So you can simply drop the type in most places where you see one.

For example, consider the following constant declaration:

```
let typeInferredInt = 42
```

Sometimes, it's useful to check the inferred type of a variable or constant. You can do this in a playground by holding down the **Option** key and clicking on the variable's or constant's name. Xcode will display a popover like this:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659808-b3a7da3e-af0c-40e5-a5c8-e41a2d144c40.png">

Xcode tells you the inferred type by giving you the declaration that you would have had to use if there were no type inference. In this case, the type is Int.

It works for other types, too:

```
let typeInferredDouble = 3.14159
```

Option-clicking on this reveals the following:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171659841-6a1aa84c-4d33-4e91-965c-896592db031c.png">

Type inference isn't magic. Swift is simply doing what your brain does very easily. Programming languages that don't use type inference can often feel verbose, because you need to specify the often obvious type each time you declare a variable or constant.

Sometimes, you want to define a constant or variable and ensure it's a certain type, even though what you're assigning to it is a different type. You saw earlier how you can convert from one type to another. For example, consider the following:

```
let wantADouble = 3
```

Here, Swift infers the type of wantADouble as Int. But what if you wanted Double instead?

What you could do is the following:

```
let actuallyDouble = Double(3)
```

This is the same as you saw before with type conversion.

Another option would be not to use type inference at all and do the following:

```
let actuallyDouble: Double = 3
```

There is a third option, like so:

```
let actuallyDouble = 3  as  Double
```

This uses a new keyword you haven't seen before, as, which also performs a type conversion.

**Note**: Literal values like 3 don't have a type. It's only when using them in an expression, or assigning them to a constant or variable, that Swift infers a type for them.

A literal number value that doesn't contain a decimal point can also be used as an Int and as a Double. This is why you're allowed to assign the value 3 to constant actuallyDouble.

Literal number values that *do* contain a decimal point cannot be integers. This means you could have avoided this entire discussion had you started with:

```
let wantADouble = 3.0
```

Sorry! (Not sorry!) :]

**Strings**
-----------

Numbers are essential in programming, but they aren't the only type of data that you need to work with in your apps. Text is also an extremely common data type, such as people's names, their addresses or even the words of a book. All of these are examples of text that an app might need to handle.

Most computer programming languages store text in a data type called a **string**. This part of the tutorial introduces you to strings by showing you how to use them in Swift.

**Strings in Swift**
--------------------

Swift, like any good programming language, can work directly with characters and strings. It does so through the data types Character and String, respectively. In this section, you'll learn about these data types and how to work with them.

### **Characters and Strings**

The Character data type can store a single character. For example:

```
let characterA: Character = "a"
```

This stores the character **a**. It can hold any character --- even an emoji:

```
let characterDog: Character = "🐶"
```

But this data type is designed to hold only single characters. The String data type, on the other hand, stores multiple characters. For example:

```
let stringDog: String = "Dog"
```

The right-hand side of this expression is what's known as a **string literal**; it's the Swift syntax for representing a string.

Of course, type inference applies here as well. If you remove the type in the above declaration, then Swift does the right thing and makes the stringDog a String constant:

```
let stringDog = "Dog"  // Inferred to be of type String
```

**Note**: There's no such thing as a character literal in Swift. A character is simply a string of length one. However, Swift infers the type of any string literal to be String, so if you want a Character instead, you must make the type explicit.

### **Concatenation**

You can do much more than create simple strings. Sometimes, you need to manipulate a string, and one common way to do so is to combine it with another string.

In Swift, you do this in a rather simple way: by using the addition operator. Just as you can add numbers, you can add strings:

```
var message = "Hello" + " my name is "
let name = "Lorenzo"
message += name // "Hello my name is Lorenzo"
```

You need to declare message as a variable rather than a constant because you want to modify it. You can add string literals together, as in the first line, and you can add string variables or constants together, as in the last line.

It's also possible to add characters to a string. However, Swift's strictness with types means you have to be explicit when doing so, just as you have to be when you work with numbers if one is an Int and the other is a Double.

To add a character to a string, you do this:

```
let exclamationMark: Character = "!"
message += String(exclamationMark) // "Hello my name is Lorenzo!"
```

With this code, you explicitly convert the Character to a String before you add it to message.

### **Interpolation**

You can also build up a string by using **interpolation**, which is a special Swift syntax that lets you build a string in a way that's easy to read:

```
let name = "Lorenzo"
let messageInOne = "Hello my name is \(name)!"  // "Hello my name is Lorenzo!"

```
The above is much more readable than the example from the previous section. It's an extension of the string literal syntax, whereby you replace certain parts of the string with other values. You enclose the value you want to give the string in parentheses preceded by a backslash.

This syntax works in just the same way to build a string from other data types, such as numbers:

```
let oneThird = 1.0 / 3.0
let oneThirdLongString = "One third is \(oneThird) as a decimal."
```

Here, you use a Double in the interpolation. At the end of this code, your oneThirdLongString constant will contain the following:

One third is 0.3333333333333333 as a decimal.

Of course, it would actually take infinite characters to represent one third as a decimal, because it's a repeating decimal. String interpolation with a Double gives you no way to control the precision of the resulting string.

This is an unfortunate consequence of using string interpolation; it's simple to use, but offers no ability to customize the output.

### **Multi-line Strings**

Swift has a neat way to express strings that contain multiple lines. This can be rather useful when you need to put a very long string in your code.

You do it like so:

```
let bigString = """
  You can have a string
  that contains multiple
  lines
  by
  doing this.
  """
print(bigString)
```

The three double-quotes signify that this is a multi-line string. Handily, the first and final new lines do not become part of the string. This makes it more flexible as you don't have to have the three double-quotes on the same line as the string.

In the case above, it will print the following:

You can have a string

that contains multiple

lines

by

doing this.

Notice that the two-space margin in the multi-line string literal is stripped out of the result. Swift looks at the number of leading spaces on the final three double-quotes line. Using this as a baseline, Swift requires that all lines above it have at least that much space so that it can remove it from each line. This lets you format your code with pretty indentation without affecting the output.

**Tuples**
----------

Sometimes, data comes in pairs or triplets. An example of this is a pair of (x, y) coordinates on a 2D grid. Similarly, a set of coordinates on a 3D grid is comprised of an x-value, a y-value and a z-value.

In Swift, you can represent such related data in a very simple way through the use of a **tuple**.

A tuple is a type that represents data composed of more than one value of any type. You can have as many values in your tuple as you like. For example, you can define a pair of 2D coordinates wherein each axis value is an integer, like so:

```
let coordinates: (Int, Int) = (2, 3)
```

The type of coordinates is a tuple containing two Int values. The types of the values within the tuple, in this case Int, are separated by commas surrounded by parentheses. The code for creating the tuple is much the same, with each value separated by commas and surrounded by parentheses.

Type inference can infer tuple types, too:

```
let coordinatesInferred = (2, 3) // Inferred to be of type (Int, Int)
```

You could similarly create a tuple of Double values, like so:

```
let coordinatesDoubles = (2.1, 3.5) // Inferred to be of type (Double, Double)
```

Or you could mix and match the types comprising the tuple, like so:

```
let coordinatesMixed = (2.1, 3) // Inferred to be of type (Double, Int)
```

And here's how to access the data inside a tuple:

```
let coordinates = (2, 3)
let x1 = coordinates.0
let y1 = coordinates.1
```

You can reference each item in the tuple by its position in the tuple, starting with zero. So, in this example, x1 will equal 2 and y1 will equal 3.

**Note**: Starting with zero is a common practice in computer programming and is called **zero indexing**.

In the previous example, it may not be immediately obvious that the first value, at index 0, is the x-coordinate and the second value, at index 1, is the y-coordinate. This is another demonstration of why it's important to always name your variables in a way that avoids confusion.

Fortunately, Swift allows you to name the individual parts of a tuple and you can be explicit about what each part represents. For example:

```
let coordinatesNamed = (x: 2, y: 3) // Inferred to be of type (x: Int, y: Int)
```

Here, the code annotates the values of coordinatesNamed to contain a label for each part of the tuple.

Then, when you need to access each part of the tuple, you can access it by its name:

```
let x2 = coordinatesNamed.x
let y2 = coordinatesNamed.y
```

This is much clearer and easier to understand. More often than not, it's helpful to name the components of your tuples.

If you want to access multiple parts of the tuple at the same time, as in the examples above, you can also use a shorthand syntax to make it easier:

```
let coordinates3D = (x: 2, y: 3, z: 1)
let (x3, y3, z3) = coordinates3D
```

This declares three new constants, x3, y3 and z3, and assigns each part of the tuple to them in turn. The code is equivalent to the following:

```
let coordinates3D = (x: 2, y: 3, z: 1)
let x3 = coordinates3D.x
let y3 = coordinates3D.y
let z3 = coordinates3D.z
```

If you want to ignore a certain element of the tuple, you can replace the corresponding part of the declaration with an underscore. For example, if you were performing a 2D calculation and wanted to ignore the z-coordinate of coordinates3D, then you'd write the following:

```
let (x4, y4, _) = coordinates3D
```

This line of code only declares x4 and y4. The _ is special and simply means that you're ignoring this part for now.

**Note**: You'll find that you can use the underscore --- also called the **wildcard operator** --- throughout Swift to ignore a value.

**A Peek Behind the Curtains: Protocols**
-----------------------------------------

Even though there are a dozen different numeric types, they are pretty easy to understand and use. This is because they all roughly support the same operations. In other words, once you know how to use an Int, using any one of the flavors is very straightforward.

One of the truly great features of Swift is how it formalizes the idea of type commonality using what are called **protocols**. By learning a protocol, you instantly understand how an entire family of types that use that protocol work.

In the case of integers, the functionality can be diagrammed like so:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171660007-bec8035c-b96d-47c7-baaa-a20c67e3a0e8.png">

The arrows indicate conformance to (sometimes called *adoption of*) a protocol. While this graph does not show all of the protocols that integer types conform to, it gives you insight into how things are organized.

Swift is the first protocol-based language. As you begin to understand the protocols that underly the types, you can start leveraging the system in ways not possible with other languages.

### **Boolean Operators**

Booleans are commonly used to compare values. For example, you may have two values and you want to know if they're equal: either they are (true) or they aren't (false).

In Swift, you do this using the **equality operator**, which is denoted by ==:

```
let doesOneEqualTwo = (1 == 2)
```

Swift infers that doesOneEqualTwo is a Bool. Clearly, 1 does not equal 2, and therefore doesOneEqualTwo will be false.

Similarly, you can find out if two values are *not* equal using the != operator:

```
let doesOneNotEqualTwo = (1 != 2)
```

This time, the comparison is true because 1 does not equal 2, so doesOneNotEqualTwo will be true.

The prefix ! operator, also called the not-operator, toggles true to false and false to true. Another way to write the above is:

```
let alsoTrue = !(1 == 2)
```

Because 1 does not equal 2, (1==2) is false, and then ! flips it to true.

Two more operators let you determine if a value is greater than (>) or less than (<) another value. You'll likely know these from mathematics:

```
let isOneGreaterThanTwo = (1 > 2)
let isOneLessThanTwo = (1 < 2)
```

And it's not rocket science to work out that isOneGreaterThanTwo will equal falseand isOneLessThanTwo will equal true.

There's also an operator that lets you test if a value is less than *or* equal to another value: <=. It's a combination of < and ==, and will therefore return true if the first value is either less than the second value or equal to it.

Similarly, there's an operator that lets you test if a value is greater than or equal to another --- you may have guessed that it's >=.

### **Boolean Logic**

Each of the examples above tests just one condition.

One way to combine conditions is by using **AND**. When you AND together two Booleans, the result is another Boolean. If both input Booleans are true, then the result is true. Otherwise, the result is false.

In Swift, the operator for Boolean AND is &&, used like so:

```
let and = true && true
```

In this case, and will be true. If either of the values on the right was false, then and would be false.

Another way to combine conditions is by using **OR**. When you OR together two Booleans, the result is true if *either* of the input Booleans is true. Only if *both*input Booleans are false will the result be false.

In Swift, the operator for Boolean OR is ||, used like so:

```
let or = true || false
```

In this case, or will be true. If both values on the right were false, then orwould be false. If both were true, then or would still be true.

**The if Statement**
--------------------

The first and most common way of controlling the flow of a program is through the use of an **if**** statement**, which allows the program to do something only *if* a certain condition is true. For example, consider the following:

```
if  2 > 1 { 
    print("Yes, 2 is greater than 1.")
}
```

This is a simple if statement. If the condition is true, then the statement will execute the code between the braces. If the condition is false, then the statement won't execute the code between the braces. It's as simple as that!

You can extend an if statement to provide code to run in case the condition turns out to be false. This is known as the **else clause**. Here's an example:

```
let animal = "Fox"

if animal == "Cat" || animal == "Dog" {
    print("Animal is a house pet.")
} else {
    print("Animal is not a house pet.")
}
```

Here, if animal equals either "Cat" or "Dog", then the statement will run the first block of code. If animal does not equal either "Cat" or "Dog", then the statement will run the block inside the else part of the if statement, printing the following to the debug area:

Animal is not a house pet.

But you can go even further than that with if statements. Sometimes you want to check one condition, then another. This is where **else-if** comes into play, nesting another if statement in the else clause of a previous if statement.

You can use it like so:

```
let hourOfDay = 12
let timeOfDay: String

if hourOfDay < 6 {
  timeOfDay = "Early morning"
} else  if hourOfDay < 12 {
  timeOfDay = "Morning"
} else  if hourOfDay < 17 {
  timeOfDay = "Afternoon"
} else  if hourOfDay < 20 {
  timeOfDay = "Evening"
} else  if hourOfDay < 24 {
  timeOfDay = "Late evening"
} else {
  timeOfDay = "INVALID HOUR!"
}
print(timeOfDay)
```

These nested if statements test multiple conditions one by one until a true condition is found. Only the code associated with that first true condition is executed, regardless of whether subsequent else-if conditions are true. In other words, the order of your conditions matters!

You can add an else clause at the end to handle the case where none of the conditions are true. This else clause is optional if you don't need it; in this example you *do* need it, to ensure that timeOfDay has a valid value by the time you print it out.

In this example, the if statement takes a number representing an hour of the day and converts it to a string representing the part of the day to which the hour belongs. Working with a 24-hour clock, the statements are checked one-by-one in order:

- The first check is to see if the hour is less than 6. If so, that means it's early morning.

- If the hour is not less than 6, the statement continues to the first else-if, where it checks the hour to see if it's less than 12.

- Then in turn, as conditions prove false, the statement checks the hour to see if it's less than 17, then less than 20, then less than 24.

- Finally, if the hour is out of range, the statement prints that information to the console.

In the code above, the hourOfDay constant is 12. Therefore, the code will print the following:

Afternoon

Notice that even though both the hourOfDay < 20 and hourOfDay < 24 conditions are also true, the statement only executes the first block whose condition is true; in this case, the block with the hourOfDay < 17 condition.

### **Encapsulating Variables**

if statements introduce a new concept **scope**, which is a way to encapsulate variables through the use of braces.

Let's take an example. Imagine you want to calculate the fee to charge your client. Here's the deal you've made:

You earn $25 for every hour up to 40 hours, and $50 for every hour thereafter.

Using Swift, you can calculate your fee in this way:

```
var hoursWorked = 45

var price = 0
if hoursWorked > 40 {
    let hoursOver40 = hoursWorked - 40
    price += hoursOver40 * 50
    hoursWorked -= hoursOver40
}
price += hoursWorked * 25

print(price)
```

This code takes the number of hours and checks if it's over 40. If so, the code calculates the number of hours over 40 and multiplies that by $50, then adds the result to the price. The code then subtracts the number of hours over 40 from the hours worked. It multiplies the remaining hours worked by $25 and adds that to the total price.

In the example above, the result is as follows:

1250

The interesting thing here is the code inside the if statement. There is a declaration of a new constant, hoursOver40, to store the number of hours over 40. Clearly, you can use it inside the if statement. But what happens if you try to use it at the end of the above code?

```
print(price)
print(hoursOver40)
```

This would result in the following error:

Use of unresolved identifier 'hoursOver40'

This error informs you that you're only allowed to use the hoursOver40 constant within the scope in which it was created. In this case, the if statement introduced a new scope, so when that scope is finished, you can no longer use the constant.

However, each scope can use variables and constants from its parent scope. In the example above, the scope inside of the if statement uses the price and hoursWorked variables, which you created in the parent scope.

### **The Ternary Conditional Operator**

Now I want to introduce a new operator, one you didn't see in the previous tutorial. It's called the **ternary conditional operator** and it's related to if statements.

If you wanted to determine the minimum and maximum of two variables, you could use if statements, like so:

```
let a = 5
let b = 10

let  min: Int
if a < b {
    min = a
} else {
    min = b
}

let  max: Int
if a > b {
    max = a
} else { 
    max = b
}
```

By now you know how this works, but it's a lot of code. Wouldn't it be nice if you could shrink this to just a couple of lines? Well, you can, thanks to the ternary conditional operator!

The ternary conditional operator takes a condition and returns one of two values, depending on whether the condition was true or false. The syntax is as follows:

```
(<CONDITION>) ? <TRUE  VALUE> : <FALSE  VALUE>
```

You can use this operator to rewrite your long code block above, like so:

```
let a = 5
let b = 10

let  min = a < b ? a : b
let  max = a > b ? a : b
```

In the first example, the condition is a < b. If this is true, the result assigned back to min will be the value of a; if it's false, the result will be the value of b.

I'm sure you agree that's much simpler! This is a useful operator that you'll find yourself using regularly.

**Note**: Because finding the greater or smaller of two numbers is such a common operation, the Swift standard library provides two functions for this purpose: max and min. If you were paying attention earlier in this series, then you'll recall you've already seen these.

**Loops**
---------

Loops are Swift's way of executing code multiple times. In this section, you'll learn about one type of loop, the while loop. If you know another programming language, you'll find the concepts and maybe even the syntax to be familiar.

### **While Loops**

A **while**** loop** repeats a block of code while a condition is true.

You create a while loop this way:

```
while <CONDITION> {
  <LOOP  CODE>
}
```

Every iteration, the loop checks the condition. If the condition is true, then the loop executes and moves on to another iteration. If the condition is false, then the loop stops. Just like if statements, while loops introduce a scope.

The simplest while loop takes this form:

```
while  true {

}
```

This is a while loop that never ends because the condition is always true. Of course, you would never write such a while loop, because your program would spin forever! This situation is known as an **infinite loop**, and while it might not cause your program to crash, it will very likely cause your computer to freeze.

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171660095-c28dc7d9-6a8e-4ebd-9678-b3e79dfa3901.png">

Here's a more useful example of a while loop:

```
var sum = 1

while sum < 1000 {
  sum = sum + (sum + 1)
}
```

This code calculates a mathematical sequence, up to the point where the value is greater than 1000.

The loop executes as follows:

- **Before iteration 1:**  sum = 1, loop condition = true

- **After iteration 1:**  sum = 3, loop condition = true

- **After iteration 2:**  sum = 7, loop condition = true

- **After iteration 3:**  sum = 15, loop condition = true

- **After iteration 4:**  sum = 31, loop condition = true

- **After iteration 5:**  sum = 63, loop condition = true

- **After iteration 6:**  sum = 127, loop condition = true

- **After iteration 7:**  sum = 255, loop condition = true

- **After iteration 8:**  sum = 511, loop condition = true

- **After iteration 9:**  sum = 1023, loop condition = false

After the ninth iteration, the sum variable is 1023, and therefore the loop condition of sum < 1000 becomes false. At this point, the loop stops.

### **Breaking Out of a Loop**

Sometimes you want to break out of a loop early. You can do this using the break statement, which immediately stops the execution of the loop and continues on to the code after the loop.

For example, consider the following code:

```
var sum = 1

while  true {
  sum = sum + (sum + 1)
  if sum >= 1000 {
    break
  }
}
```

Here, the loop condition is true, so the loop would normally iterate forever. However, the break means the while loop will exit once the sum is greater than or equal to 1000. Neat!

**Ranges**
----------

Before you dive into the for loop statement, you need to know about the **Range**data type, which lets you represent a sequence of numbers. Let's look at two types of Range.

First, there's **closed range**, which you represent like so:

```
let closedRange = 0...5
```

The three dots (...) indicate that this range is closed, which means the range goes from 0 to 5 inclusive. That's the numbers (0, 1, 2, 3, 4, 5).

Second, there's half-open range, which you represent like so:

```
let halfOpenRange = 0..<5
```

Here, you replace the three dots with two dots and a less-than sign (..<). Half-open means the range goes from 0 to 5, inclusive of 0 but *not* of 5. That's the numbers (0, 1, 2, 3, 4).

Both open and half-open ranges must always be increasing. In other words, the second number must always be greater than or equal to the first.

Ranges are commonly used in both for loops and switch statements, which means that throughout the rest of this section, you'll use ranges as well!

**For Loops**
-------------

In the previous section, you looked at while loops. Now that you know about ranges, it's time to look at another type of loop: the **for**** loop**. This is probably the most common loop you'll see, and you'll use it to run code a certain number of times.

You construct a for loop like this:

```
for <CONSTANT> in <RANGE> {
  <LOOP  CODE>
}
```

The loop begins with the for keyword, followed by a name given to the loop constant (more on that shortly), followed by in, followed by the range to loop through.

Here's an example:

```
let  count = 10
var sum = 0

for i in  1...count {
  sum += i
}
```

In the code above, the for loop iterates through the range 1 to count. At the first iteration of the loop, i will equal the first element in the range: 1. Each time around the loop, i will increment until it's equal to count; the loop will execute one final time and then finish.

**Note:** If you'd used a half-open range, the the last iteration would see i equal to count - 1.

Inside the loop, you add i to the sum variable; it runs 10 times to calculate the sequence 1 + 2 + 3 + 4 + 5 + ... all the way up to 10.

Here are the values of the constant i and variable sum for each iteration:

- **Start of iteration 1:**  i = 1, sum = 0

- **Start of iteration 2:**  i = 2, sum = 1

- **Start of iteration 3:**  i = 3, sum = 3

- **Start of iteration 4:**  i = 4, sum = 6

- **Start of iteration 5:**  i = 5, sum = 10

- **Start of iteration 6:**  i = 6, sum = 15

- **Start of iteration 7:**  i = 7, sum = 21

- **Start of iteration 8:**  i = 8, sum = 28

- **Start of iteration 9:**  i = 9, sum = 36

- **Start of iteration 10:**  i = 10, sum = 45

- **After iteration 10:**  sum = 55

In terms of scope, the i constant is only visible inside the scope of the for loop, which means it's not available outside of the loop.

**Note:** If you're mathematically astute, you might notice that this example computes **triangle numbers**. Here's a quick explanation: <http://bbc.in/1O89TGP>

Xcode's playground gives you a handy way to visualize such an iteration. Hover over the sum += i line in the results pane, and you'll see a white dot on the right. Hover over that dot to reveal a plus (+) button:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171660184-5421b310-03ef-40fa-8995-0ade7cc0604d.png">

Click this plus (+) button and Xcode will display a graph underneath the line within the playground code editor:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/88003574/171660207-a3bd1d60-acff-4a29-8b81-c90fb014546c.png">

This graph lets you visualize the sum variable as the loop iterates.

Finally, sometimes you only want to loop a certain number of times, and so you don't need to use the loop constant at all. In that case, you can employ the underscore to indicate you're ignoring it, like so:

```
let  count = 10
var sum = 1
var lastSum = 0

for  _  in  0..<count {
  let temp = sum
  sum = sum + lastSum
  lastSum = temp
```

This code doesn't require a loop constant; the loop simply needs to run a certain number of times. In this case, the range is 0 through count and is half-open. This is the usual way of writing loops that run a certain number of times.

It's also possible to only perform the iteration under certain conditions. For example, imagine you wanted to compute a sum similar to that of triangle numbers, but only for odd numbers:

```
let  count = 10
var sum = 0
for i in  1...count  where i % 2 == 1 {
  sum += i
}
```

The loop above has a where clause in the for loop statement. The loop still runs through all values in the range 1 to count, but it will only execute the loop's code block when the where condition is true; in this case, where i is odd.

**Switch Statements**
---------------------

Another way to control flow is through the use of a switch statement, which lets you execute different bits of code depending on the value of a variable or constant.

Here's a very simple switch statement that acts on an integer:

```
let number = 10

switch number {
case  0:
  print("Zero")
default:
  print("Non-zero")
}
```

In this example, the code will print the following:

Non-zero

The purpose of this switch statement is to determine whether or not a number is zero. It will get more complex --- I promise!

To handle a specific case, you use case followed by the value you want to check for, which in this case is 0. Then, you use default to signify what should happen for all other values.

Here's another example:

```
let number = 10

switch number {
case  10:
  print("It's ten!")
default:
  break
}
```

This time you check for 10, in which case, you print a message. Nothing should happen for other values. When you want nothing to happen for a case, or you want the default state to run, you use the break statement. This tells Swift that you *meant* to not write any code here and that nothing should happen. Cases can never be empty, so you *must* write some code, even if it's just a break!

Of course, switch statements also work with data types other than integers. They work with any data type! Here's an example of switching on a string:

```
let string = "Dog"

switch string {
case  "Cat", "Dog":
  print("Animal is a house pet.")
default:
  print("Animal is not a house pet.")
}
```

This will print the following:

Animal is a house pet.

In this example, you provide two values for the case, meaning that if the value is equal to either "Cat" or "Dog", then the statement will execute the case.

### **Advanced Switch Statements**

You can also give your switch statements more than one case. In the previous section, you saw an if statement using multiple else-if statements to convert an hour of the day to a string describing that part of the day. You could rewrite that more succinctly with a switch statement, like so:

```
let hourOfDay = 12
let timeOfDay: String

switch hourOfDay {
  case  0, 1, 2, 3, 4, 5:
  timeOfDay = "Early morning"
case  6, 7, 8, 9, 10, 11:
  timeOfDay = "Morning"
case  12, 13, 14, 15, 16:
  timeOfDay = "Afternoon"
case  17, 18, 19:
  timeOfDay = "Evening"
case  20, 21, 22, 23:
  timeOfDay = "Late evening"
default:
  timeOfDay = "INVALID HOUR!"
}

print(timeOfDay)
```

This code will print the following:

Afternoon

Remember ranges? Well, you can use ranges to simplify this switch statement. You can rewrite it using ranges as shown below:

```
let hourOfDay = 12
let timeOfDay: String

switch hourOfDay {
case  0...5:
  timeOfDay = "Early morning"
case  6...11:
  timeOfDay = "Morning"
case  12...16:
  timeOfDay = "Afternoon"
case  17...19:
  timeOfDay = "Evening"
case  20..<24:
  timeOfDay = "Late evening"
default:
  timeOfDay = "INVALID HOUR!"
}
```

This is more succinct than writing out each value individually for all cases.

When there are multiple cases, the statement will execute the first one that matches. You'll probably agree that this is more succinct and more clear than using an if statement for this example. It's slightly more precise as well, because the if statement method didn't address negative numbers, which here are correctly deemed to be invalid.

It's also possible to match a case to a condition based on a property of the value. As you learned in the first part of this tutorial series, you can use the modulo operator to determine if an integer is even or odd. Consider this code:

```
let number = 10

switch number {
case  let x where x % 2 == 0:
  print("Even")
default:
  print("Odd")
}
```

This will print the following:

Even

This switch statement uses the let-where syntax, meaning the case will match only when a certain condition is true. The let part binds a value to a name, while the where part provides a Boolean condition that must be true for the case to match. In this example, you've designed the case to match if the value is even --- that is, if the value modulo 2 equals 0.

The method by which you can match values based on conditions is known as **pattern matching**.

In the previous example, the binding introduced a unnecessary constant x; it's simply another name for number. You are allowed to use number in the whereclause and replace the binding with an underscore to ignore it:

```
let number = 10

switch number {
case  _  where number % 2 == 0:
  print("Even")
default: 
  print("Odd")
}
```

### **Partial Matching**

Another way you can use switch statements with matching to great effect is as follows:

```
let coordinates = (x: 3, y: 2, z: 5)

switch coordinates {
case (0, 0, 0): // 1
  print("Origin")
case (_, 0, 0): // 2
  print("On the x-axis.")
case (0, _, 0): // 3
  print("On the y-axis.")
case (0, 0, _): // 4
  print("On the z-axis.")
default: // 5
  print("Somewhere in space")
}
```

This switch statement makes use of **partial matching**. Here's what each case does, in order:

1. Matches precisely the case where the value is (0, 0, 0). This is the origin of 3D space.

2. Matches y=0, z=0 and any value of x. This means the coordinate is on the x-axis.

3. Matches x=0, z=0 and any value of y. This means the coordinate is on the y-axis.

4. Matches x=0, y=0 and any value of z. This means the coordinate is on the z-axis.

5. Matches the remainder of coordinates.

You're using the underscore to mean that you don't care about the value. If you don't want to ignore the value, then you can bind it and use it in your switch statement, like this:

```
let coordinates = (x: 3, y: 2, z: 5)

switch coordinates {
case (0, 0, 0):
 print("Origin")
case (let x, 0, 0):
 print("On the x-axis at x = \(x)")
case (0, let y, 0):
 print("On the y-axis at y = \(y)")
case (0, 0, let z):
 print("On the z-axis at z = \(z)")
case  let (x, y, z):
 print("Somewhere in space at x = \(x), y = \(y), z = \(z)")
}
```

Here, the axis cases use the let syntax to pull out the pertinent values. The code then prints the values using string interpolation to build the string.

Notice how you don't need a default in this switch statement. This is because the final case is essentially the default; it matches anything, because there are no constraints on any part of the tuple. If the switch statement exhausts all possible values with its cases, then no default is necessary.

Also notice how you could use a single let to bind all values of the tuple: let (x, y, z) is the same as (let x, let y, let z).

Finally, you can use the same let-where syntax you saw earlier to match more complex cases. For example:

```
let coordinates = (x: 3, y: 2, z: 5)

switch coordinates {
case  let (x, y, _) where y == x:
 print("Along the y = x line.")
case  let (x, y, _) where y == x * x:
 print("Along the y = x^2 line.")
default:
 break
```

} Here, you match the "y equals x" and "y equals x squared" lines.

And those are the basics of switch statements!

**Enumerations**
================

An *enumeration* defines a common type for a group of related values and enables you to work with those values in a type-safe way within your code.

If you are familiar with C, you will know that C enumerations assign related names to a set of integer values. Enumerations in Swift are much more flexible, and do not have to provide a value for each case of the enumeration. If a value (known as a "raw" value) *is* provided for each enumeration case, the value can be a string, a character, or a value of any integer or floating-point type.

Alternatively, enumeration cases can specify associated values of *any* type to be stored along with each different case value, much as unions or variants do in other languages. You can define a common set of related cases as part of one enumeration, each of which has a different set of values of appropriate types associated with it.

Enumerations in Swift are first-class types in their own right. They adopt many features traditionally supported only by classes, such as computed properties to provide additional information about the enumeration's current value, and instance methods to provide functionality related to the values the enumeration represents. Enumerations can also define initializers to provide an initial case value; can be extended to expand their functionality beyond their original implementation; and can conform to protocols to provide standard functionality.

For more about these capabilities, see [Properties](https://docs.swift.org/swift-book/LanguageGuide/Properties.html), [Methods](https://docs.swift.org/swift-book/LanguageGuide/Methods.html), [Initialization](https://docs.swift.org/swift-book/LanguageGuide/Initialization.html), [Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html), and [Protocols](https://docs.swift.org/swift-book/LanguageGuide/Protocols.html).

**Enumeration Syntax**
----------------------

You introduce enumerations with the enum keyword and place their entire definition within a pair of braces:

```
enum  SomeEnumeration {
 // enumeration definition goes here
}
```

Here's an example for the four main points of a compass:

```
enum  CompassPoint {
 case north
 case south
 case east
 case west
}
```

The values defined in an enumeration (such as north, south, east, and west) are its *enumeration cases*. You use the case keyword to introduce new enumeration cases.

Multiple cases can appear on a single line, separated by commas:

```
enum  Planet {
 case mercury, venus, earth, mars, jupiter, saturn, uranus, neptune
}
```

Each enumeration definition defines a new type. Like other types in Swift, their names (such as CompassPoint and Planet) should start with a capital letter. Give enumeration types singular rather than plural names, so that they read as self-evident:

```
var directionToHead = CompassPoint.west
```

The type of directionToHead is inferred when it is initialized with one of the possible values of CompassPoint. Once directionToHead is declared as a CompassPoint, you can set it to a different CompassPoint value using a shorter dot syntax:

```
directionToHead = .east
```

The type of directionToHead is already known, and so you can drop the type when setting its value. This makes for highly readable code when working with explicitly typed enumeration values.

**Matching Enumeration Values with a Switch Statement**
-------------------------------------------------------

You can match individual enumeration values with a switch statement:

```
directionToHead = .south
switch directionToHead {
case .north:
 print("Lots of planets have a north")
case .south:
 print("Watch out for penguins")
case .east:
 print("Where the sun rises")
case .west:
 print("Where the skies are blue")
}
// Prints "Watch out for penguins"
```

You can read this code as:

"Consider the value of directionToHead. In the case where it equals .north, print "Lots of planets have a north". In the case where it equals .south, print "Watch out for penguins"."

...and so on.

As described in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html), a switch statement must be exhaustive when considering an enumeration's cases. If the case for .west is omitted, this code does not compile, because it does not consider the complete list of CompassPoint cases. Requiring exhaustiveness ensures that enumeration cases are not accidentally omitted.

When it is not appropriate to provide a case for every enumeration case, you can provide a default case to cover any cases that are not addressed explicitly:

```
let somePlanet = Planet.earth
switch somePlanet {
case .earth:
  print("Mostly harmless")
default:
  print("Not a safe place for humans")
}
// Prints "Mostly harmless"
```

Enums are one of the most powerful tools on swift, they have many more functionalities and aplications, for more information about enums visit: <https://docs.swift.org/swift-book/LanguageGuide/Enumerations.html>

**Optionals**
-------------

You use *optionals* in situations where a value may be absent. An optional represents two possibilities: Either there *is* a value, and you can unwrap the optional to access that value, or there *isn't* a value at all.

Here's an example of how optionals can be used to cope with the absence of a value. Swift's Int type has an initializer which tries to convert a String value into an Int value. However, not every string can be converted into an integer. The string "123" can be converted into the numeric value 123, but the string "hello, world" doesn't have an obvious numeric value to convert to.

The example below uses the initializer to try to convert a String into an Int:

```
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// convertedNumber is inferred to be of type "Int?", or "optional Int"
```

Because the initializer might fail, it returns an *optional* Int, rather than an Int. An optional Int is written as Int?, not Int. The question mark indicates that the value it contains is optional, meaning that it might contain *some* Int value, or it might contain *no value at all*. (It can't contain anything else, such as a Bool value or a String value. It's either an Int, or it's nothing at all.)

### **nil**

You set an optional variable to a valueless state by assigning it the special value  nil:

```
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value
```

NOTE

You can't use nil with nonoptional constants and variables. If a constant or variable in your code needs to work with the absence of a value under certain conditions, always declare it as an optional value of the appropriate type.

If you define an optional variable without providing a default value, the variable is automatically set to nil for you:

```
var surveyAnswer: String?
// surveyAnswer is automatically set to nil
```

NOTE

Swift's nil isn't the same as nil in Objective-C. In Objective-C, nil is a pointer to a nonexistent object. In Swift, nil isn't a pointer---it's the absence of a value of a certain type. Optionals of *any* type can be set to nil, not just object types.

### **If Statements and Forced Unwrapping**

You can use an if statement to find out whether an optional contains a value by comparing the optional against nil. You perform this comparison with the "equal to" operator (==) or the "not equal to" operator (!=).

If an optional has a value, it's considered to be "not equal to" nil:

```
if convertedNumber != nil { 
    print("convertedNumber contains some integer value.")
}
// Prints "convertedNumber contains some integer value."
```

Once you're sure that the optional *does* contain a value, you can access its underlying value by adding an exclamation mark (!) to the end of the optional's name. The exclamation mark effectively says, "I know that this optional definitely has a value; please use it." This is known as *forced unwrapping* of the optional's value:

```
if convertedNumber != nil {
    print("convertedNumber has an integer value of \(convertedNumber!).")
}
// Prints "convertedNumber has an integer value of 123."
```

For more about the if statement, see [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

NOTE

Trying to use ! to access a nonexistent optional value triggers a runtime error. Always make sure that an optional contains a non-nil value before using ! to force-unwrap its value.

### **Optional Binding**

You use *optional binding* to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with if and while statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action. if and while  statements are described in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

Write an optional binding for an if statement as follows:

```
if  let constantName = someOptional {
   statements
}
```

You can rewrite the possibleNumber example from the [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID330) section to use optional binding rather than forced unwrapping:

```
if  let actualNumber = Int(possibleNumber) {
    print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")
} else {
    print("The string \"\(possibleNumber)\" could not be converted to an integer")
}
// Prints "The string "123" has an integer value of 123"
```

This code can be read as:

"If the optional Int returned by Int(possibleNumber) contains a value, set a new constant called actualNumber to the value contained in the optional."

If the conversion is successful, the actualNumber constant becomes available for use within the first branch of the if statement. It has already been initialized with the value contained *within* the optional, and so there's no need to use the ! suffix to access its value. In this example, actualNumber is simply used to print the result of the conversion.

You can use both constants and variables with optional binding. If you wanted to manipulate the value of actualNumber within the first branch of the if statement, you could write if var actualNumber instead, and the value contained within the optional would be made available as a variable rather than a constant.

You can include as many optional bindings and Boolean conditions in a single if  statement as you need to, separated by commas. If any of the values in the optional bindings are nil or any Boolean condition evaluates to false, the whole if statement's condition is considered to be false. The following if statements are equivalent:

```
if  let firstNumber = Int("4"), let secondNumber = Int("42"), firstNumber < secondNumber && secondNumber < 100 {
    print("\(firstNumber) < \(secondNumber) < 100")
}
// Prints "4 < 42 < 100"

if  let firstNumber = Int("4") {
    if  let secondNumber = Int("42") {
        if firstNumber < secondNumber && secondNumber < 100 {
            print("\(firstNumber) < \(secondNumber) < 100")
        }
    }
}
// Prints "4 < 42 < 100"
```

NOTE

Constants and variables created with optional binding in an if statement are available only within the body of the if statement. In contrast, the constants and variables created with a guard statement are available in the lines of code that follow the guard statement, as described in [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525).

### **Implicitly Unwrapped Optionals**

As described above, optionals indicate that a constant or variable is allowed to have "no value". Optionals can be checked with an if statement to see if a value exists, and can be conditionally unwrapped with optional binding to access the optional's value if it does exist.

Sometimes it's clear from a program's structure that an optional will *always* have a value, after that value is first set. In these cases, it's useful to remove the need to check and unwrap the optional's value every time it's accessed, because it can be safely assumed to have a value all of the time.

These kinds of optionals are defined as *implicitly unwrapped optionals*. You write an implicitly unwrapped optional by placing an exclamation mark (String!) rather than a question mark (String?) after the type that you want to make optional.

Implicitly unwrapped optionals are useful when an optional's value is confirmed to exist immediately after the optional is first defined and can definitely be assumed to exist at every point thereafter. The primary use of implicitly unwrapped optionals in Swift is during class initialization, as described in [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55).

An implicitly unwrapped optional is a normal optional behind the scenes, but can also be used like a nonoptional value, without the need to unwrap the optional value each time it's accessed. The following example shows the difference in behavior between an optional string and an implicitly unwrapped optional string when accessing their wrapped value as an explicit String:

```
let possibleString: String? = "An optional string."

let forcedString: String = possibleString! // requires an exclamation mark

let assumedString: String! = "An implicitly unwrapped optional string."

let implicitString: String = assumedString // no need for an exclamation mark
```

You can think of an implicitly unwrapped optional as giving permission for the optional to be unwrapped automatically whenever it's used. Rather than placing an exclamation mark after the optional's name each time you use it, you place an exclamation mark after the optional's type when you declare it.

NOTE

If an implicitly unwrapped optional is nil and you try to access its wrapped value, you'll trigger a runtime error. The result is exactly the same as if you place an exclamation mark after a normal optional that doesn't contain a value.

You can still treat an implicitly unwrapped optional like a normal optional, to check if it contains a value:

```
if assumedString != nil {
    print(assumedString!)
}
// Prints "An implicitly unwrapped optional string."
```

You can also use an implicitly unwrapped optional with optional binding, to check and unwrap its value in a single statement:

```
if  let definiteString = assumedString {
    print(definiteString)
}
// Prints "An implicitly unwrapped optional string."
```

NOTE

Don't use an implicitly unwrapped optional when there's a possibility of a variable becoming nil at a later point. Always use a normal optional type if you need to check for a nil value during the lifetime of a variable.

Further Reading
---------------

- [Structs and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)
- [Functions](https://docs.swift.org/swift-book/LanguageGuide/Functions.html)
- [Closures](https://docs.swift.org/swift-book/LanguageGuide/Closures.html)
