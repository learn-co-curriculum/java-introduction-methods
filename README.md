# Introduction to Methods

## Learning Goals

- Explain what a method is in Java.
- Describe the method header.

## Introduction

We have been hearing about methods in previous lessons, let's now finally dive
into what a method actually is in Java!

## What is a Method?

A **method** is a way to group statements together so that they can be called
upon as a group any time we need them to be executed.

When we create a program, we give the computer instructions on what to do in a
specific language, in our case in Java. To do so, Java gives us access to
built-in functionality, such as the ability to print a message to a screen:

```java
System.out.println("this message will be displayed as text on the screen"); 
```

`println()` is a method - it has statements inside it that allow it to tell
the computer to print the desired message on the screen. Those statements, the
ones inside `println()`, might be complex. But since they are wrapped up in a
method, we can simply call that method without knowing how it is fully
implemented.

## Method Headers

Before we can write a method ourselves, we need to understand the method header.

![method-header](https://curriculum-content.s3.amazonaws.com/java-mod-1/method/Method-Header.png)

### Access Modifiers

Every method has an access modifier. We'll learn more about access modifiers
later on. But if we look at the `main()` method:
`public static void main(String[] args)` know that the keyword, `public` is
considered an access modifier. In this lesson, that is the only access modifier
we will look at. We'll also use it in conjunction with the `static` keyword.
Again, more on those keywords later on.

### Return Values

A method can return a value after it's done executing. In Java, we want to
specify what data type is to be returned once the method has completed. We call
this a **return type**. It may return another object, a primitive, or even
nothing!

Consider the `println()` method for example. The job of the `println()` method is
to print text to the console. Once it's done performing that work, it simply
returns the execution to the method that called it without returning any value.
This is expressed in the header of the method with the `void` keyword:

```java
public void thisMethodReturnsNothing() {
    System.out.println("I print something on the screen, and then return nothing");     
} 
```

Another example is the `public static void main(String[] args)` method we have
been referring to. This method also makes use of the `void` return type to tell
us that it will not have a return value when the program finishes executing.

Here are a few rules to remember about method return types:

- A method must always have a return type, but that type can be `void` to
  specify that the method does not return anything.
- A method return type can be any valid Java type, which means it can be any
  pre-defined Java type or any of our own classes we create. More on that point
  later.
- If a method is declared with a return type other than `void`, it _must_ return
  a value compatible with that type.

### Method Name

The **method name** is what we want to call our method. When naming methods,
it is best to be descriptive yet concise with the action that is to be performed
inside the method. For example, if we expect the method to cook us some food, we
should not name the method `x()` but rather `cook()`.

Simplifying the method name, yet being descriptive with the name to make it clear
to other developers is very helpful.

Method names should also follow the same naming conventions of variables. In
Java, the name of the method usually starts with a lowercase character. If the
name of the method has multiple words in it, the first word will start with a
lowercase character and every word after will start with an uppercase character.
For example: `cookEggs()`. This naming convention is referred to as
**camel case**.

### Parameter List

A **parameter list** is a list of the declarations needed for the method to
function properly. A method can take in as many parameters as it needs to
function properly. Each parameter in the parameter list needs to be in a
declaration format as such: `<type> <variableName>`. It is also possible to not
have a parameter list. An empty parameter list would look like this: `()`. If
multiple parameters exist, then they are to be separated by a comma `,` between
each parameter. Example: `cook(String breakfastItem1, String breafastItem2)`.

In the `public static void main(String[] args)` method, we can see that this
method does indeed have some parameters associated with it. It looks like the
`main()` method takes in a parameter `String[] args`. `args` is the variable
name and has the data type of `String[]`. We haven't yet learned about the
symbol `[]`, but know that this parameter is saying it takes in an array of
`String` values. The array of `String` values is called `args` because it
represents the arguments that can be passed into the program when it is run
from the command line. We will learn more about this in a later unit, so we can
ignore the `args` variable for now, just know that it does need to be part of
the method definition for the `main()` method.

Note: **Parameters** refers to the list of variables in a method declaration.
**Arguments** are the actual values that are passed in when the method is
invoked. When a method is invoked, the arguments used must match the
declaration's parameters in type and order.

Now that we have defined the method header defined, we can see how to write a
method!

## Conclusion

Methods are a way for us to call a specific block of statements that we want to
execute together. Java has some built-in methods that we have been using with
certain utilities, like the `println()` method and the `nextLine()` method. But
we can also create our own methods - we'll look more in-depth of reading and
writing methods in the next few lessons!
