# Common Types - List

In C#, a List is much like the arrays that you used in other languages. They are collections of a objects that are all of a specific type.

* List of integers(numbers)
* List of strings(words)
* List of booleans(true/false)
* List of Customers(unique objects)

lists can **only contain** one type. ie every item in the list has to be ALL numbers or another type.  A list CANNOT be a collection of integers *and* strings.

```cs
// Totally fine code
List<int> yearsBorn = new List<int>() {
    1967, 1969, 1972
};
```

This code will produce red squiggles(error, computer is confused) under 1967 and 1972. C# has no default way to convert a string into an integer, and it will tell you that.

```cs
// Bogus code
List<int> yearsBorn = new List<int>() {
    "1967", 1969, "1972"
};
```

## A More Powerful Array

You can use [arrays](https://docs.microsoft.com/en-us/dotnet/api/system.array?view=netcore-2.1) in C#, as well.

```cs
int[] itemsSold = new int[] {9, 12, 8, 8, 7, 14, 13, 9};
```

The downside to using arrays in C#, in particular for web application development, is that is not as easy to add and remove items from an array as it is when you use a `List`.

The `List` collection in C# has the following methods that an array does not.
The below methods are built-in functions that preform an operation on every item in a list.

* [Add()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.add?view=netcore-2.1)
* [AddRange()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.addrange?view=netcore-2.1)
* [Insert()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.insert?view=netcore-2.1)
* [Find()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.find?view=netcore-2.1)
* [Remove()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.remove?view=netcore-2.1)
* [Contains()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.contains?view=netcore-2.1)
* [ForEach()](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.foreach?view=netcore-2.1)
* [Count](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.count?view=netcore-2.1)

```cs
using System.Collections.Generic;

namespace NSSOrientation
{
    public class Program
    {
        public static void Main()
        {
            List<string> students = new List<string>() {
                "Megan", "Damon", "Chase", "Tekisha",
                "Castle", "Mark", "Keith", "Adam",
                "Patrick", "Hannah", "Mike"
            }

            // Can't do this easily with a base array
            students.Add("Melanie");
            students.Insert(3, "Simon");

            if (students.Contains("Chase")) {
                Console.WriteLine("Must be cohort 13");
            }

            // This looks a lot like JavaScript!
            students.ForEach(stu => Console.WriteLine(stu));
        }
    }
}
```

## Reference

* [C# Lists](https://msdn.microsoft.com/en-us/library/6sh2ey19(v=vs.110).aspx)
* [Interactive C# Lists](http://www.learncs.org/en/Lists)

# Practice: Planet and Spaceships

## Setup

```
create new project in Visual Studio 2019 -- C# Console App .NET Core
name project chapter4practice or just practice if you created a folder called 'chapter4'
```

## Instructions

In the `Main` method, place the following code

```cs
List<string> planetList = new List<string>(){"Mercury", "Mars"};
```

1. `Add()` Jupiter and Saturn at the end of the list.
1. Create another `List` that contains that last two planet of our solar system.
1. Combine the two lists by using `AddRange()`.
1. Use `Insert()` to add Earth, and Venus in the correct order.
1. Use `Add()` again to add Pluto to the end of the list.
1. Now that all the planets are in the list, slice the list using `GetRange()` in order to extract the rocky planets into a new list called `rockyPlanets`. The rocky planets will remain in the original planets list.
1. Being good amateur astronomers, we know that Pluto is now a dwarf planet, so use the `Remove()` method to eliminate it from the end of `planetList`.

# Practice: Random Numbers


## Instructions -- add this code in same project as planets, so when you run the program, the console prints out all the planets AND prints out the Random Numbers
## OR
## create two projects, one named planets and the other called randomNumbers
## we will work on these together in class but after this chapter I will live-code for the first 30 minutes and give a short lecture on the fundament(s) we will cover that day(whiteboard), and then set you loose to complete the chapter exercises and practice for the last 1.5 hours of class. 


1. Use the following code to create a list of random numbers. Each number will be between 0 and 5.
    ```cs
    Random random = new Random();
    List<int> numbers = new List<int> {
        random.Next(6),
        random.Next(6),
        random.Next(6),
        random.Next(6),
        random.Next(6),
        random.Next(6),
    };
    ```

    ```cs
    for (int i=0; i<numbers.Count; i++) {
       // Determine if the current loop index is contained inside of the `numbers` list. Print a message to the console indicating whether the index is in the list.
       
    }
    ```

#### Example Output in the Terminal
```sh
numbers list contains 0
numbers list does not contain 1
numbers list does not contain 2
numbers list contains 3
numbers list contains 4
numbers list does not contains 5
```
**NOTE:** Each time you run the program, it will produce different numbers each time you press run(CTRL-f5)

 
> **Further Reading**
> [Random class in .net](https://docs.microsoft.com/en-us/dotnet/api/system.random?view=netframework-4.7.2)
