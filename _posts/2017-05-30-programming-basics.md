---
layout: post
title: Programming Basics - variables, operators and functions
---
### A Program Statement

A statement on a program is simply a piece of code that causes an action. Usually, a statement is a line of code. For example:

    console.log('Some message');

Causes "Some message" to be logged to the console. Or

    x = y + 5;

Will cause a "variable" `x` to have a value equal to the variable `y` plus 5.

Programming then, is simply the act of putting statements together in such an order that the computer will output a desired result. This is harder than it first appears, as computers are thoroughly stupid, and thoroughly obedient. Whatever you tell them to do, will be done, whether it is beneficial to your program or not. The art of programming is in undestanding a problem to the level that you can express it to a computer at the simplest level. This comes through consistent practice. In this assignment we are more concerned with the mechanics of programming and the tools available to help you express those instructions.

### Program variables

When developing a program, the programmer is often simply shuffling data around from one form to another. It is therefore convenient to have a way of storing and representing data inside the program. This is achieved using "variables". A variable is simply a label, any label, given to a piece of data you're working with. For example if a programmer wanted to write a simple statement to output a persoinalised greeting, it might look something like this:


    var name = 'Mr McBlokeFace';
    console.log("Hello " + name);


The variable `username` is simply a label to hold the data. The program would work the same if it were written:


    var person = 'Mr McBlokeFace';
    console.log("Hello " + person);


or


    var x = 'Mr McBlokeFace';
    console.log("Hello " + x);


However, it is always preferable to use a name which expresses your intent to the programmers who will work with your code after you are finished.

In Javascript, variables must be declared before they can be used. This is achieved using the special language keyword `var` as in the example above. You can assign and declare a variable at the same time, or you can simply declare an empty variable for future use. For example:


    // declare only
    var username;

    // declare and assign
    var username = "Some username";


Variables are assigned values using the `=` operator, as in `x = 5` or `name = 'Barry'` or `newThing = oldThing`.

### Data and variable types

In the real world, you deal with differing types of data all the time and your brain (usually) knows how to deal with them intrinsically. For example, you know that numbers can be added, and you can do this mentally with varying degrees of accuracy, however if I told you my phone number, you would also know that adding it to another number, whilst possible, is likely to be nonsensical.

Computers do not have this implicit knowledge, and so need to be told what form a piece of data is. We achieve this with the concept of "types". Javascript as a language uses a fairly typical set of types. These are:

#### Number

When using whole numbers (integers),  for example `4` or `1234512597`, Numbers are used as in everyday life, although due to memory constraints they do have an upper and lower limit. When numbers contain decimal components though, for example `3.14159265359` or `2.71828`, they are similar to numbers used in everyday maths, but due to how they are represented in memory, they are not always as accurate as one would expect. Javascript stores all numbers as floating point representations, which is beyond the scope if this assignment. You should know though, that any functionality depending on decimal point arithmetic should be thoroughly tested for accuracy.

#### String

A string is any series of characters. For example `"Hello, Barry"` or `"01208 73100"` or `"☠💩L"`. Strings can contain any characters that the computer can represent and are used for storing names, addresses and any written content. Note that numbers can often be stored in memory as strings, and will need conversion to integers or floats before any mathematical operations can be carried out, to a computer `5` is not the same as `'5'`. In examples here, string will be written in quote marks `'like this'` or double quotes `"like this"`. Javascript has no preference between the two, so long as the opening and closing quotes match.

#### Boolean

This type will always be either `true` or `false`. These are more useful than they first apper when it comes to program flow and you will come across them often.

#### Null

This is a special type, used to represent nothing of any type.

#### Undefined

Another special type. This is what you receive when you try to reference a variable that has not been declared yet. The underlying engine does not have any reference to the variable you are looking for and so returns `Undefined`.

#### Object

These also exist, more on these in future assignments!

#### Array

These also exist, more on these in future assignments!


### Operators available

This is a short list of common operators that you may find in use in Javascript. It is not exhaustive, but it is a powerful set of the available commands available to you.

| Operator | Purpose                                                                                                                                               |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| `=`      | Used for assigning, as in `x = 8` or `you = 'awesome'`                                                                                                |
| `+`      | Used for mathematical addition, and also string concatenation. For example `7 + 3` will yield `10`, where `'hello' + 'Barry' will yield `helloBarry`. |
| `-`      | Used for mathematical subtraction                                                                                                                     |

| `*`      | Used for mathematical multiplication (`5 * 3` yields `15`).                                                                                           |
| `/` | Used for mathematical division (`10 / 5` yields `2`). |
| `%` | Used to calculate the modulus (or remainder) of a division. For example `10 % 3` yields `1`, where `15 % 3` yields `0`. |
| `++` | Increment, will add one to a variables value. For example |
|     | x = 5; |
|     | x++; // yields 6 |
|     | x++; // yields 7 |
|`--` | Decrement, will subtract one from a variables value. As in `x--` |
|`===` | Equality test. Will yield true if two operands are equal. As in |
|      | var x = 5; |
|      | x === 5; // yields true |
|      | x = 8; |
|      | x === 5; // yields false |
|`!==` | Not equal. Will yield false if two operands are equal. |
|`>` | Greater than |
|`>=` | Greater than or equal to |
|`<` | Less than |
|`<=` | Less than or equal to |
|`&&` | Logical "and", used for determining if multiple operands are all true. For example:
|     |  x = true; |
|     |  y = true; |
|     |  x && y; // yields true |
|     | |
|     |  y = false; |
|     |  x && y; // yields false |
|`!` | Logical "Not" operator. Will reverse the boolean value of something. For example:
| | x = true; |
| | y = !x; // y is now set to false |
|`||` | Logical "or", used for determining if any operands from a set are true. |

### Functions

When a programmer wishes to reuse a set of statements, they can group them together into a function. This is simply a named set of statements, which take a known set of values to work with. The name can be anything you care to use, provided it does not conflict with existing function names.

When declaring a function, you can consider it as a contract between the function and the code that will be calling it. Your function is promising that, if you provide some specified parameters, it will carry out some specified operation. Sometimes, functions will need return a value on completion, sometimes they will not. For example, a function named `addNumbers` is likely to return the product of that addition back to the caller. Whereas a function `console.log` is concerned solely with outputting data to the user, and may not return anything to the program that called it.

Declaring functions can be done in a few ways in javascript, but the most common are the following two:

    function addNumbers(x, y) {
        return x + y;
    }
    var addNumbers = function(x, y) {
        return x + y;
    };


Both of the above are identical in use. Both declare a function named `addNumbers` and both have two "parameters" that they will accept: `x` and `y`. Of note is the special language keyword `return` which is used to send data back to the caller on completion of the function. This not only returns that value, but also signals the end of the function, so any statements after the return will not be executed.

As with variables, the names can be anything you desire, but should be easy to understand for future programmers. The naming of functions and their parts looks like this:

    function someNameYouInvent(parameter, parameter) {
        statement;
        statement;
        statement;
        return statement or return value;
    }

The `function` keyword is there to tell the computer that you are defining a function here, the name is used to refer to that function later on, and the parameters are used to pass data into the function when called. When you're writing the function, you don't know yet exactly what the data will be, but you can add comments to your code to indicate the type of data you expect, or make it clear through the functions name (in the example case, we expect Numbers).

(You should also really check that the data you have been given is within the expected range, to ensure your funciton operates as expected, although this is out of scope of this assignment.)

To muddy the waters, javascript also allows "anonymous" functions which have no name. These will come up later.

Once you have declared a function, you will want to "invoke" it. This means, call it and use it. To invoke the above function I would write `addNumbers(13, 5)` which would yield `18`; I could also write:

    var x = 13;
    var y = 5;
    addNumbers(x, y);

and achieve the same result, as the variable values will be passed in to the function.
