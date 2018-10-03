# Eggshell
Eggshell is currently under construction. Please come back when I've had my next coffee and made the first (major) commit.

## The idea of Eggshell
Eggshell works on the concept of nesting taken to its extreme. Every class (excluding the `root` class) resides within another and can contain its own code (executed upon construction), as well as more classes. This means that every method is its own class and "invoking" a method is done by constructing a new instance of it. It's more of an experiment than anything else, don't expect to be able to actually do anything useful with this.

## Current mockup
Here's a mockup example of some Eggshell code, showcasing some incredibly basic elements like classes, variables, including, etc.:

```
class root.main(root.array<root.string> args){ //Create main as a child of root - this class will be instantiated to start the program
  #root //Include root for access to loops, basic types etc.
  #root.math //Include math for access to arithmetic, numeral types etc.
  var sum = 0 //Define a new variable, sum, as an integer with value 0
  forEach(args, var s, { //Using the foreach class. It takes an array, a variable and some code as arguments.
    ## //Since the code inside the foreach is its own class, we must include its parent (two hash symbols includes the parent class)
    sum = add(sum, s.toInt()) //Convert each argument into an int, then add it to the sum
  })
  println(sum) //Print the result
  //Since there is no return statement in main, it will return void()
}
```
As a side note, this will change quite a bit as I figure out how the language will work.
