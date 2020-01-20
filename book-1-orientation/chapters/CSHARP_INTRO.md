# Not Hello, World

## Getting Started Guide

Please read and complete the steps in the official [Get Started with C# and Visual Studio Code](https://docs.microsoft.com/en-us/dotnet/core/tutorials/with-visual-studio-code) guide.

## Setup

Make a directory(new folder) called "IT242" -- this is where you will save all of your work for this class


We're going to get your first C# console application setup and running so that we can review some basics of the language.

1. Open Visual Studio 2019(purple icon)
2. select "create new project"
3. Select "Console App(.NET Core)
4. Name your project "basicCsharp" and save it in a new folder (ie. IT242/Book1/Chapter2) and press "create"
5. should see code that looks like this...

```
using System;

namespace basicCsharp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

in searchbar type in "solution explorer" and open it

when you created your project, VS(Visual Studio) automatically creates a few files
two important files in the directory are...

1. `intro.csproj` - This file holds all the packages that you application will be using. It's the `package.json` for C#.
1. `Program.cs` - This is the file that holds your logic. Think of it as your `main.js`. It's where the logic of your application starts.

Change "Hello World" -> "Welcome to IT242, where we will learn to build and we will like it!"
```

        public static void Main(string[] args)
        {
            Console.WriteLine("Welcome to IT242, where we will learn to build and we will like it!");
        }


```

> ☞ C# is a compiled language, meaning that you need a compiler to read the source code, parse all the logic, and then construct a new executable file.

Now you press the "Play" symbol(located at the top, sideways green triangle) to build and run your new console app!!

You should see `Welcome to IT242, where we will learn to build and we will like it!` print out in your terminal.

OPTIONAL -- in searchbar type "Package Manager Console" --(PMC is an integrate terminal) -- select this and a window should pop up at the bottom of the screen, now enter these commands below
```do a quick -- ls -- this lists all files in the current directory
make sure you see a file ending in .sln 
then type "dotnet build" -- make sure it says zero errors
then cd into the sotutions folder(it should be what you named your project ie. "basicCsharp" -> cd basicCsharp
do another "ls" look for a file named "Program.cs" -- cs stands for C#
last step: type "dotnet run" and you should see "welcome to IT242...like it" printed to the PMC
```


## Strongly Typed Variable in C#

Now replace your source code with the following.

```cs
using System;

namespace bangazon
{
    class Program
    {
        static void Main(string[] args)
        {
            // DateTime is the type of the purchaseData variable.
            DateTime purchaseDate=DateTime.Now;

            /*
                string is the type of the lastName variable. It
                tells the compiler that the lastName variable can
                ONLY hold a string value.
            */
            string lastName="Smith";

            /*
                C# now supports implicitly typing of a variable. The
                type of the variable will be determined, by the
                compiler, at compile time.
            */
            var firstName="Bill";

            /*
                String interpolation in C# is similar to string interpolation in JavaScript,
                but there is a different syntax.

                An equivalent statement in JavaScript would be:
                console.log(`${firstName} ${lastName} purchased on ${purchaseDate}`);
            */
            Console.WriteLine($"{firstName} {lastName} purchased on {purchaseDate}");
        }
    }
}
```

# C# Collections and Loops

The C# language has many ways to store a collection of items. You'll quickly see that C# is verbose when you write your source code, because the developer needs to provide all of the instructions to the compiler, unlike JavaScript or other dynamically typed languages.


We'll look at a simple type of collection first - list of strings. Add the following code to your `Main` method.

```cs
/*
    Not only do you have to say what type the variable is, you also
    have to instantiate that exact same type of object on assignment.
    This may seem redundant, but it's part of the C# language compiler's
    type checking constraints.
*/
List<string> products = new List<string>() {
    "Motorcycle",
    "Sofa",
    "Sandals",
    "Omega Watch",
    "iPhone"
};

/*
    A foreach loop is used to iterate over a collection.

    The code below is roughly equivalent to the following JavaScript:
    products.forEach(product => {
        console.log(product);
    });
*/
foreach (string product in products) {
    Console.WriteLine(product);
}

/*
    Like JavaScript, C# has a for() loop

    This code is equivalent to the foreach loop above.
*/
for (int i=0; i<products.Count; i++) {
    Console.WriteLine(products[i]);
}
```

# C# Conditions

Luckily, the `if-then` syntax works exactly like it did in JavaScript. 
Let's display a different message based on on the length of a product.

```cs
foreach (string product in products) {
    if (product.Length < 5) {
        Console.WriteLine($"{product} has a short name");
    } else if (product.Length < 10) {
        Console.WriteLine($"{product} has a medium-sized name");
    } else {
        Console.WriteLine($"{product} has a long name");
    }
}
```

# Resources

I strongly recommend that you bookmark the following web page.

[C# Programming Guide](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/index)
