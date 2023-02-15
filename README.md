# Introduction to Methods

## Learning Goals

- Explain what a method is in Java.
- Describe the method header.
- Discuss how to write methods.

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

## Method Headers and Writing Methods

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

Now that we have defined the method header defined, we can see how to write a
method!

### Writing Methods

Let us consider a scenario where we want to greet some neighbors to a
neighborhood block party!

We can create a method that prints a message, "Welcome neighbors!" like so:

```java
public class Main {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void main(String[] args) {
        welcome();
    }
}
```

Notice that the method is defined **outside** the `main()` method. This is so
we can actually _call_ the method within the `main()` method. The `welcome()`
method will not be invoked or executed until we call it elsewhere in the code.
As we can see, we call a static method by simply writing out the method name
and its parameters where we want to execute the method's block statements.

If we look closer at the `welcome()` method we created, we'll notice that it
does not return anything based on the `void` return type. Instead, all it will
do is print the message "Welcome neighbors!"

Let us see what happens when we run this method:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=1&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

If we click "Next >", we will see the execution jumps up to the first line in
the `welcome()` method! When we continue clicking the "Next >" button, we will
see it print out the message "Welcome neighbors!" and then return to the bottom
of the `main()` method.

Let's continue this block party example! Assume a neighbor is walking around and
asking each guest what they would like cooked on the grill. Let's create a
method to print out what someone would like cooked:

```java
public class Main {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }
    
    // New method
    public static void cook(String food) {
        System.out.println("Okay, I can cook " + food);
    }

    public static void main (String[] args) {
        welcome();
        cook("Hot dogs");    // Call the new method cook()
    }
}
```

In the above code, we created a new method called `cook()` that takes in 1
parameter: `String food`. We can pass in the type of food we want cooked when we
call the `cook()` method like so: `cook("Hot dogs")`. Notice that we pass in a
`String` data type. Remember, the data types need to match what is defined in
the method header.

Let's step through the code and see what happens when we call the `cook()`
method:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20//%20New%20method%0A%20%20%20%20public%20static%20void%20cook%28String%20food%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Okay,%20I%20can%20cook%20%22%20%2B%20food%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%20%20%20%20cook%28%22Hot%20dogs%22%29%3B%20%20%20%20//%20Call%20the%20new%20method%20cook%28%29%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

Notice when we click "Next >", the execution jumps to the `cook()` method. But
also note that the `food` variable parameter is now set to `"Hot dogs"`. In the
`main()` method, we call the `cook()` method and pass in the parameter "Hot
dogs". This value then gets copied when calling the `cook()` method and assigns
the parameter variable, `food` to "Hot dogs".

![call-cook-method](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods/java-visualizer-method-parameter.png)

If we continue to click "Next >" we'll see the new output of our block party
program:

```text
Welcome neighbors!
Okay, I can cook Hot dogs
```

We can slightly modify the code as such:

```java
public class Main {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void cook(String food) {
        System.out.println("Okay, I can cook " + food);
    }

    public static void main (String[] args) {
        String hotDogs = "Hot dogs";    // Store "Hot dogs" in a local variable
        welcome();
        cook(hotDogs);    // Pass in the local variable
    }
}
```

This code will perform the same output as before. Except this time, we will pass
in a variable that holds the value "Hot dogs".

![call-method-cook-with-local-variable](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods/java-visualizer-method-parameter-local-variable.png)

Notice the variable `hotDogs` sitting on the stack. When we call the `cook()`
method, the value of `hotDogs` will get "copied" into the `food` variable. Java
will proceed with the execution in the same way we saw prior.

Let's write one more method in our block party example. Let's have this method
return a headcount of the number of neighbors that attended the party.

```java
public class Main {

    public static void welcome() {
        System.out.println("Welcome neighbors!");
    }

    public static void cook(String food) {
        System.out.println("Okay, I can cook " + food);
    }
    
    // New method with return statement
    public static int headcount() {
        return 20;
    }

    public static void main (String[] args) {
        String hotDogs = "Hot dogs";
        welcome();
        cook(hotDogs);
        int neighbors = headcount();    // Calling the headcount method and assigning to neighbors
        System.out.println("There are " + neighbors + " neighbors in attendance.");
    }
}
```

Notice that the `headcount()` method does not have a `void` return type. This
means it is intending on returning something! The method header:
`public static int headcount()` states that the `headcount()` method will return
an `int` data type. This means it _must_ return an `int` data type. If it did
not, we'd end up with a compiler-error saying:

```text
java: missing return statement
```

The `return` keyword is used to return a specific value from a method. Note that
the `return` keyword interrupts the execution of the current method and returns
the specified value to the caller (i.e. the method that called this method). In
this example, we are expected to return an `int` data type. Hence, we return
`20`.

Also notice that since the `headcount()` method returns an `int`, we can assign
the `int` that `headcount()` returns to a new variable where the method is
called: `int neighbors = headcount();`

Let's step through the code one more time to see what happens when the `main()`
method calls the `headcount()` method:

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%0A%20%20%20%20public%20static%20void%20welcome%28%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Welcome%20neighbors!%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20cook%28String%20food%29%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Okay,%20I%20can%20cook%20%22%20%2B%20food%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20//%20New%20method%20with%20return%20statement%0A%20%20%20%20public%20static%20int%20headcount%28%29%20%7B%0A%20%20%20%20%20%20%20%20return%2020%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%20%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20String%20hotDogs%20%3D%20%22Hot%20dogs%22%3B%0A%20%20%20%20%20%20%20%20welcome%28%29%3B%0A%20%20%20%20%20%20%20%20cook%28hotDogs%29%3B%0A%20%20%20%20%20%20%20%20int%20neighbors%20%3D%20headcount%28%29%3B%20%20%20%20//%20Calling%20the%20headcount%20method%20and%20assigning%20to%20neighbors%0A%20%20%20%20%20%20%20%20System.out.println%28%22There%20are%20%22%20%2B%20neighbors%20%2B%20%22%20neighbors%20in%20attendance.%22%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=12&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

When we click the "Next >" button, just like the other methods, we will see that
it jumps into the `headcount()` method.

What is more interesting is that if we continue clicking "Next >", we will see
the method have a return value of 20.

![return-value-20](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods/java-visualizer-return-value-20.png)

Once Java is done executing the `headcount()` method, it will return to the
`main()` method where it initializes the variable `neighbors` to the return
value of 20.

![intiialize-neighbors-variable](https://curriculum-content.s3.amazonaws.com/java-mod-1/methods/java-visualizer-initialize-neighbors.png)

When we resume this program, it will print the following output:

```text
Welcome neighbors!
Okay, I can cook Hot dogs
There are 20 neighbors in attendance.
```

It's important to understand that any statement after a `return` statement
does not get executed. For example, the following code will not compile because
the code after the `return` statement can never be reached by the JVM and is
therefore considered invalid:

```java
    public static int headcount() {
        return 20;
        System.out.println("Thanks for coming!");
    }
```

We could also return a value of a local variable to the `headcount` method as
such:

```java
    public static int headcount() {
        int count = 20;
        return count;
    }
```

This would still result in `20` being returned. This also shows how we can
create our own methods and have multiple statements be executed in one method
block.

## Conclusion

Methods are a way for us to call a specific block of statements that we want to
execute together. Java has some built-in methods that we have been using with
certain utilities, like the `println()` method and the `nextLine()` method. But
we can also create our own methods as we have done here.
