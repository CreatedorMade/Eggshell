# Eggshell
Eggshell is currently under construction. Please come back when I've had my next coffee and made the first (major) commit.

## The idea of Eggshell
Eggshell works on the concept of nesting taken to its extreme. Every class (excluding the `root` class) resides within another and can contain its own code (executed upon construction), as well as more classes. This means that every method is its own class and "invoking" a method is done by constructing a new instance of it. It's more of an experiment than anything else, don't expect to be able to actually do anything useful with this.

## Current mockup
Here's a mockup example of some Eggshell code, showcasing some incredibly basic elements like classes, variables, including, etc.:

```
class root.main{ //Create main as a child of root - this class will be instantiated to start the program
  include root; //Include the root and math libraries for access to loops, adding etc.
  include root.math;
  (array<string> args){ //The constructor for main, which takes the commandline arguments as an array of strings
    sum = int(0) //Define the variable sum as 0
    foreach(args, var s, (){ //Using the foreach method. It takes an array, a variable, and a method
      sum = add(sum, s.toInt()) //Convert each string in args to an int, then add each one to sum
    })
    println(sum.toString()) //Print sum
  }
}
```
