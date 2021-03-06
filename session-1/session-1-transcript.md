# Intro to JS: Session 1

## Outline
 - Introduction
  - My Mentors
  - Course Overview and Goals
 - Why JavaScript
 - What is JavaScript
  - History
 - Syntax
 - Variables
 - Data Types
  - Primitive and Reference Values
  - Primitive Types
  - Reference Types
  - Operators
  - Flow Control Statements
 - Exercise 1
 - Execution Context (Scope)
 - Functions
 - Exercise 2
 - Objects
 - Prototypes and Delegation
 - 'this'
 - Pseudoclassical Pattern
 - Exercise 3

## Introduction

Hello everyone, and welcome to "Introduction to JavaScript", or alternately titled "How I learned to Stop Worrying and Love the JavaScript." My name is Miles Dickinson, and my first introduction to JavaScript as a sophmore in high school when I started developing websites. My first few years with the language was a struggle, because I made a fundamental mistake that is made by many professional programmers today. I tried to use the language without understanding it. That is the core reason for many negative things you may think or have heard about JavaScript.

JavaScript is famous for both being the world's most misunderstood programming language, and having more good parts and bad parts than any other language. Over the next four sessions, I am going to teach a combination of the good parts, and the parts you will most likely encounter in the wild. There are some parts of the languge I will not be covering both for the sake of time, and you'll never want to program with them anyway. But as you continue your education in JavaScript I encourage to learn about them for learning why those features are dangerous is important.

### My Mentors

I want to take a second to introduce you to three people you should absolutely know about in the JavaScript community. Douglas Crockford, Kyle Simpson, and Dr. Axel Rauschmayer. They're incredibly smart people, and have given enormously to the community in terms of education, open source development, and leading the future of the language. I highly recommend you look them up and check out their collective works to take your JavaScirpt to the next level.

### Course Outline and Goals

This is a four session class, and each session will have three 15 minute lectures, and three exercies.

Some of the exercies I expect you to complete in 5 minutes, some I don't, and that's okay. I'll be capping exercise time at exactly 5 minutes to stay on schedule, and we will review the solution before starting the next lecture. I also highly encourage you to revisit the exercises later today to reinforce what you've learned.

I've reserved the conference room for an extra 30 minutes for questions. If you're hear in person raise your hand, and if you're remote please mute your line and ask questions through the webex chat.

Today, in session 1 we're going to discuss what JavaScript is, why we should care, and dive into language fundamentals. We'll then examine, functions, scope, and wrap up with a look at the object system.

## What is JavaScript

Contrary to it's name, JavaScript has almost nothing to do with Java. As far as mechanics of the language, Java and JavaScript couldn't be more fundamentally different. JavaScript is a mix of Java Syntax, first class functions and lexical scope from Scheme, a protypal object system from Self, and a couple of the creators own ideas. But how did this language come to be?

### History

Let's jump back to 1995. Netscape made Navigator, one of the first popular web browsers, and they wanted to add interactivity to the next version, Navigator 2. They hired Brendan Eich for the job and he wanted to write a scheme interpreter, but Netscape thought the syntax was too weird and wanted him to use somthing more familiar like Visual Basic or Java. The langauge he wrote was a mix of three languages, Java because he had to, Scheme, and Self, and in about 10 days he had completed the first version of LiveScript. To give you a basis of comparison, smalltalk80, considered one of the best designed languages of all time, was designed in about 8 years.

Netscape wasn't alone in this space, Microsoft had Internet Explorer. Sun Microsystems, the creators of Java, and Netscape realized they needed to work together against Microsoft, so Microsoft wouldn't pit them against eachother. But the biggest area of contention between the two companies was what to do with LiveScript. Sun's position was to put Java in Netscape's browser and kill Livescript. Netscape wanted a simpler programming model to capture a wider developer base. They were at an impasse, when the suggestion came, possibly as a joke, "Lets change the name to JavaScript." And it worked.

Microsoft decided they needed to copy Netscape's model to stay competitive so they reverse engineered the JavaScript engine and called it JScript. Netscape, alarmed the language was being embraced and extended, decided it needed to be standardized, and ended up at the European Computer Manufacturer's Association. The committe created a standard, but was not able to name it JavaScript, because even though Sun tried to kill the language, they claimed trademark on the name. Therefore, the committe published the standard under the working title ECMAScript. So now we have JavaScript, JScript, and ECMAScript, and they are all the same language.

## Why JavaScript

1. JavaScript is the language of the browser. Whether you like it or not, if you want to have any client-side interactivity, you need to use JavaScript.

2. JavaScript is everywhere. It's one of the most popular languages in the world, and JavaScript runtimes are spreading everwhere from servers, robots, and even watches. This gave rise to "Atwood's Law" which states, "Any application that can be written in JavaScript, will eventually be written in JavaScript." JavaScript is also what gave rise to the concept of a full-stack developer. For the first time, we can write our entire application in one language, and the benefits of simplicity, code resuse, and not having to switch contexts as you go from client to server cannot be overstated.

3. Now that we'eve established you will most likey be working in JavaScript at some point, you can't program in a language you don't understand. Going back to understanding the langauge, a bug is simply a manifestation of confusion in your program. It's where you think your program is doing something different than it is actually doing. If you don't understand what your code is doing, how can ever know your programs will work?
 
4. The good parts are really, really good. When I mention good parts, I'm specifically talking about Douglas Crockford's "Good Parts", which is a subset of the JavaScript language where confusing and problematic features are removed. The fundamental principal behind the good parts, which I think is brilliant and should be applied to all languages, is "if you have a feature that is sometimes useful and sometimes probelmatic, and there is an alternative, always use the alternative." It's not that the bad parts of JavaScript aren't useful, it's that there's never a case where they aren't confusing. And we've already established confusion is our mortal enemy.

5. Finally, you should learn JavaScript because GE needs you to learn JavaScript. Not only for the opportunities of using JavaScript with Predix, but I have seen JavaScript in production being used in ways that i've never seen before, and that's not a good thing.


## Syntax

The fundamental building blocks of a JavaScript program are statements, which are made of one or more expressions. An expression produces a value, and a statement affects change in the world. By world, I mean the context of your program, and every statement in your program should move the problem state of your world toward its solution state. You name all the variables, functions, properties, and function arguments in your world with identifiers.

An identifier may be one or more characters in the following format:
 - The first letter must be a letter, and underscore, or a dollar sign.
 - All other characters may be letters, underscores, dollar signs, or numbers.
 - use camelCase
 - everything is case sensitive

JavaScript's syntax borrows heavily from Java and other C-like languages such as Pearl. 
Also, JavaScript uses C-style comments for single line comments `// comment here` and block level comments
```
/* 
block 
of multiple lines
*/
```

Finally, ECMAScript 5 introduced `strict-mode`, which is a differnt parsing and execution model for JavaScript where some of the troublesome behavior of 3rd edition of the standard is addressed and errors are thrown for unsafe activities. I reccommend you write all your programs in `strict-mode` if possible.

## Variables

Variables in JavaScript are loosely typed, which means that they can hold any type of data. Contrary to a strongly typed langauge like Java, where a variable must be declared to only hold a specific type. In JavaScript, a variable is simply a placeholder for a value.

To define a variable, use the `var` operator followed by a identifier.
```
// Define a variable, miles, and initialize it to "rocks"
var miles = "rocks";
```

## Data Types

### Primitive and Reference Values

Two types of values can be stored in JavaScript variables: primitive values and reference values. 

Primitive values have one of the five primitive data types: undefined, null, boolean, string, and number. They are a fixed size and are stored on the stack in memory. Copying primitive values from one variable to another creates a second copy of the value.

Reference values are objects and are stored on the heap in memory. A variable containing a reference value actually contains just a pointer to the object, not the object itself. The pointer is a variable that holds a memory address. Coying a reference value to anohter variable copies tjust the pointer, so both variables are referencing the same object.

The `typeof` operator determine's a variable's primitive type, whereas the `instaceof` operator determines the reference type of the value.

### Primitive Types

There are five simple data types, also called primitives, in JavaScript.
- `string`
- `number`
- `boolean`
- `undefined`
- `null`
And one complex data type: `object`.

The `string` data type represents a sequence of zero or more 16-bit unicode characters. Strings can be delineated by either double quotes `"` or single quotes `'`. You can also use character literals, which are a backslash `\` followed by a series of characters which represent symbols beyond those built into your keyboard. For example, `\n` represents a new line, and `\u03a3` displays equivalent to the Greek character Zeta on your screen.

Strings are immutable, meaning once they are created, their values cannot be changed. To change the string held by a variable, the original string must be destroyed and the variable filled with another string containing the new value. Concatenation is done via the `+` operator as shown in the example below:

```
var truth = "Miles";
truth = truth + " Is Great";
```

The `number` type uses the IEEE-754 format, which is known as a `double` in other languages. It uses 64 bits to represent both integers and floating-point numbers. Unlike other languages where you have to decide on a number type based on how how big you think the number is going to be, there is only one type in JavaScript, so you simply wirte the literal number. 

```
var integer = 6;
var float = 1.1;
```

The `boolean` type only has two literal values: `true` and `false`. All values, however, can be cast to a boolean, therefore values are said the be either "truthy" or "falsy" depending on whether they resolve to `true` or `false` after boolean conversion. Many of JavaScript's built in statements, such as the `if` statement perform this conversion automatically.

```
var message = "Hello World";
if (message) {
 console.log("Value is true");
}
```

The `undefined` type has only one value, which is a special value `undefined`. When a variable is declared using `var`, but not initialized (assigned to a value) it is assigned the value `undefined`.

The `null` type has only one value, a special value `null`. A `null` value is technically an empty object pointer, so the `typeof` operator, which determines the data type of a value, thinks it's type is an object. Due to this quirk, I recommend only using `undefined` as a bottom value, as it's the one the language uses interally. 

### Reference Types
- `Object`
- `Array`
- `Date`
- `RegExp`
- `Function`
- `String`
- `Number`
- `Boolean`

These reference functions create objects of the corresponding reference type. Reference types are structures used to group data and functionality together.

The `Object` type is a dynamic collection of properties and is the base for all the other reference types.

It has a number of built in methods. 
- `isPrototypeOf` - determines if the object is a prototype of another object.
- `propertyIsEnumerable` - indicates if the given property can be enumerated (retrived using a for-in loop)
- `hasOwnProperty` - indicates if the given property exists on the object instance (not on the prototype)

The perferred way to create an object is with an object literal syntax:
```
var obj = {
 prop1: 'myProperty',
 prop2: function () {
  console.log("I am also a property, sometimes called a method");
 }
};
```

The `Array` type is an ordered list of data that is dynamically sized and can hold any type of value.

It has a number of built in methods.
- `push` - add item to end of array.
- `pop` - remove and return item from end of array.
- `shift` - remove and return item from beginning of array.
- `unshift` - add item to beginning of array.

Since `instanceof` returns `object` when testing an array, we need to use Array.isArray method to determine if an array is an array.

The preferred way to create an array is with array literal syntax:
```
var arr = ['js', 'is', 'fun'];
```

The `Date` type stores dates as the number of milliseconds that have passed since midnight on January 1, 1970 UTC.

To create a new `Date` object, use the new operator with the Date reference function.
```
var now = new Date();
```

They type comes with a number of formatting methods:
 - `getDay` - returns the date's day of the week, where 0 is sunday and 6 is saturday.
 - `getHours` - returns the date's hours as a number between 0 and 59.
 - `getMinutes` - returns the date's minutes as a number.
 - `getSeconds` - returns the date's seconds as a number.

JavaScript supports regular expressions through the `RegExp` type. A regular expression is a  special string for describing a search pattern.

They are created using the following pattern:
```
// Pattern
// var expression = /pattern/flags

var expression = /miles/gi;
```

The `Function` type has properties and methods like any other reference type. Unlike many other languages, functions in JavaScript are simply callable objects. There are two ways to define a function: function declarations and function expressions. A function declaration is where function is the first word of the statement, and function expressions is when any other word comes first. For example,
```
// function declaration
function foo() {
 console.log("fighters");
}

// function expression
var foo = function () {
 console.log("fighters");
}
```
The major difference between the two forms is in how the JavaScript engine loads data into the execution context. Function declarations are read and available in an execution context before any code is executed, whereas function expressions aren't available until the execution reaches that line of code. We'll be going into much more detail on functions later.

Finally the `String`, `Number`, and `Boolean` types are known as primitive wrapper types. They convert a primitive value to it's corresponding reference type, which contain useful methods for operating on the data. This conversion can be done explicitly, by calling the function with the `new` keyword, but is also done implicitly by the language.

For example, the perferred way to convert a string to uppercase is to the use `String` type's built in method `.toUpperCase`.
```
var upperCase = "miles".toUpperCase(); // "MILES"
```
Notice that I did not need to convert the string primitive "miles" to a `String` reference type before being able to use the `toUpperCase` method, JavaScript takes care of that for me.


## Operators

Operators can be used to manipulate data. The main types of operators are arithmetic, logical, relational, and equality operators.

Arithmetic operators include addition (+), subtraction (-), multiplication (*), division (*), and modulus(%), which returns the remainder of dividing the two operands.

Logical operators can be used to create logical expressions, and include and (&&), or (||), and not (!).

Relational operators compare two values in an expression and return the result of that expression as a boolean. These include less-than (<), greater-than (>), less-than-or-equal-to (<=), and greater-than-or-equal-to (>=).

Equality operators deal with one of the most important operations in programming, determine whether two variables are equivalent. There are two equality operators double equal `==` and triple equal `===`. The difference between is `==` performs conversion on the operands before comparison, and `===` compares the values without conversion. Due to the unpredictable results of type coercion, it's recommended to only use `===`.

Finally the assignemnt operator `=` simply assigns the value on the right to the variable on the left
```
var x = 2;
```
and the comma operator `,` allows execution of more than one operation in a single statement.
```
var x = 2,
    y = 3,
    z = 4;
```

## Flow Control Statements

Flow control is the execution path your program takes depending on the state of your program. The three types of flow control are sequential, conditional, and iterative. 

Sequential flow control is the default top-to-bottom execution of your program.

Conditional flow is where one of multiple execution paths are taken due to the result of a conditional expression. JavaScript has the `if` statment, which can be pared with an `else if` and `else` to handle any number of conditions.

```
var a = 4;
var b = 3;

if (a > b) {
 console.log("a is greater than b.");
} else {
 console.log("a is less than or equal to b");
}
```

Iterative flow is where a block of statements is executed repeatedly until a condition is met. The two primary statements for iteration are the `for` and `while` loop.

```
var x = 0;
for (i = 0; i < 10; i += 1) {
 console.log('JS is da best!');
}

var y = 0;
while (y < 10) {
 console.log('JS is da best!');
 y += 1;
}
```

## Exercise 1

Our first exercise is pretty straightforward. I have defiend five tasks which give you the pseudocode, and you need to implement them in JavaScript. You have five minutes, and I recommend looking back through the slides if you get stuck on syntax.

## Exercise 1 Solution

## Execution Context (Scope)

All variables, primitive and reference, exist within an execution context (scope), which determines the lifetime of the variable and which parts of the code can access it.

JavaScript has lexical scope, and only within functions, not blocks. Scopes that are local to a function have access not only to the variables in that scope but also to variables in any outer scope, all the way up to the global scope. That accessibility known as the scope chain.

The scope of a variable helps determine when it will be released from memory. JavaScript is a garbage-collected programming environment, so the developer does not need to be concerned with memory allocation or reclamation. When values go out of scope, they will be automatically marked for reclamation and will be deleted during the garbage collection process.

## Functions

Functions are the best part of JavaScript. They combine three really powerful language features that were never before combined in a single language. Functions as first class values, lexical scope, and the ability to nest functions.

I always disliked the term "first class value", becuase i got hung up on this unknown classification system, when all it really means is that anything you can do with a regular object, or a string, or any other value, you can do with a function. That means you can assign a function to a variable, assign it to the property of an object (which gets called a method), pass it as an argument to another function, and return it from a function.

As we discussed earlier, lexical scope sets the scope of a variable so that it may only be called from within the block of code in which it is defined. In JavaScript, the only blocks that have scope are functions. Therefore, nesting functions with lexical scope allow us to define local scopes within a larger function scope. This has many uses, and we'll talk about this feature in greater depth when we get into closure next session.

Since Functions are objects, they have methods like any other object. Two such methods are `call` and `apply`, which allow you to invoke a function, and pass in an object that get assigned to the invocation object's `this` value, and any number of additional arguments. We'll get to `this` when we discuss objects after the next exercise.

## Exercise 2

## Objects

Objects are a dynamic collection of properties, each of which may contain any value. The biggeset misunderstanding in JavaScript is that it's object system is similar to Java, where you create an object by instantiating a class. Class instantiation is a copy operation, where a brand new object is created with all the properties that were defiend in the blueprint, the class.

### Protypal

JavaScript does not have classes and it does not copy. JavaScript has a protypal object system, an entirely differnt model than Java's classical model. In JavaScript, objects are linked to other objects in a chain called the "protype chain." It's similar to a linked list if you're familar with that data strucutre. Each object has an internal `[[Prototype]]` property, which contains a reference to the next link in its prototype chain. If you access a property on an object, and the object does not have the property, it will look for the property on the next object in its prototype chain. This model is of sharing functionality is called "delegation", and it's actually a much more flexibile way of sharing functionality than inheritance in Java. In Java, you need to create rigid taxonomies of types for your object system, at the beginning of your project when you have the least understanding of your problem. In JavaScript, all you need to do is change what `[[Prototype]]` points at to change an object's functionality.

### this

A feature commonly used with object systems in JavaScript is `this`. `this` is a way of implicitly "passing along" an object reference, and it can allow for cleaner api design and code reuse. `this` is probably one of the more confusing parts of the langauge, because it does not refer to the currently executing function or the function's lexical scope. `this`'s value is bound at runtime, not author time and it depends on how the function is called.

To determine how a function is called, you need to inspect the call-site. Upon inspection, there a 4 rules for determing the value of `this`. Those rules, in order of priority are:

1. New binding. This is where you make a constructor call by calling `new Function()`. The `new` operator creates a new object and assigns this to the value within the function body.
 
2. Explicit binding. This is where you use the function's `call` or `apply` methods to invoke the function and pass in a value for `this` as the first argument.

3. Implicit binding. This is where you call a method on an object. For example, the `myObj.method()` call will assign the value `myObj` to the `this` value within `method`'s function body.

4. Default binding. The default binding is where the function is called normally, `foo()`. In ES5 strict mode, `this` will be set to undefined, and set to the global object otherwise.

### Pseudoclassical Pattern

The Pseudoclassical Pattern is one of the most popular patterns for creating object systems. It's where you define a "constructor" function for your reference type which assigns data to properties on your object, and then define methods for your type on the type's prototype object. You then call the constructor function with the `new` keyword and a new object with the constructed data properties and a `[[Protype]]` link to the object you assigned methods to is created.

The syntax for the pattern is as follows:
```
// Type definiton
function Person(name, age, job) {
 this.name = name;
 this.age = age;
}

Person.prototype.sayHi = function () {
 console.log("Hi everybody");
 console.log("Hi " + this.name);
}

// Object creation
var person1 = new Person("Dr. Nick", 44);
person1.sayHi(); // "Hi everybody" "Hi Dr. Nick"

```

## Exercise 3

## Conclusion
