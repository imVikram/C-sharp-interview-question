# C-sharp-interview-question
Updated C Sharp(C#) interview questions list

| No. | Questions |
|---- | ---------|
|1    | [What is C#(C Sharp)?	](#how-do-we-create-objects-in-javascript )|


# What is C#?

C# is the best language for writing Microsoft .NET applications. C# provides the rapid application development found in Visual Basic with the power of C++. Its syntax is similar to C++ syntax and meets 100% of the requirements of OOPs like the following:

• Abstraction

• Encapsulation

• Polymorphism

• Inheritance


# What is an Object?

A class or struct definition is like a blueprint that specifies what the type can do. An object is basically a block of memory that has been allocated and configured according to the blueprint. A program may create many objects of the same class. Objects are also called instances, and they can be stored in either a named variable or in an array or collection. Client code is the code that uses these variables to call the methods and access the public properties of the object. In an object-oriented language such as C#, a typical program consists of multiple objects interacting dynamically


# What is the difference between a struct and a class in C#

Struct

• The struct is value type in C# and it inherits from System.Value Type.

• Struct is usually used for smaller amounts of data.

• Struct can’t be inherited to other type.

• A structure can't be abstract.

• No need to create object by new keyword.

• Do not have permission to create any default constructor.

Class

• The class is reference type in C# and it inherits from the System.Object Type.

• Classes are usually used for large amounts of data.

• Classes can be inherited to other class.

• A class can be abstract type.

• We can’t use an object of a class with using new keyword.

• We can create a default constructor.


# What is the difference between Interface and Abstract Class?

# An abstract class-

An abstract class is a special kind of class that cannot be instantiated. So the question is why we need a class that cannot be instantiated? An abstract class is only to be sub-classed (inherited from). In other words, it only allows other classes to inherit from it but cannot be instantiated. The advantage is that it enforces certain hierarchies for all the subclasses. In simple words, it is a kind of contract that forces all the subclasses to carry on the same hierarchies or standards.

# An Interface

An interface contains only the signatures of methods, properties, events or indexers. A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition. In the following example, class ImplementationClass must implement a method named SampleMethod that has no parameters and returns void.

# The difference

An interface is not a class. It is an entity that is defined by the word Interface. An interface has no implementation; it only has the signature or in other words, just the definition of the methods without the body. As one of the similarities to Abstract class, it is a contract that is used to define hierarchies for all subclasses or it defines specific set of methods and their arguments. The main difference between them is that a class can implement more than one interface but can only inherit from one abstract class. Since C# doesn't support multiple inheritance, interfaces are used to implement multiple inheritance.

When we create an interface, we are basically creating a set of methods without any implementation that must be overridden by the implemented classes. The advantage is that it provides a way for a class to be a part of two classes: one from inheritance hierarchy and one from the interface.

When we create an abstract class, we are creating a base class that might have one or more completed methods but at least one or more methods are left uncompleted and declared abstract. If all the methods of an abstract class are uncompleted then it is same as an interface. The purpose of an abstract class is to provide a base class definition for how a set of derived classes will work and then allow the programmers to fill the implementation in the derived classes.
## Example:

```csharp

interface  <interface_name >
{
    // declare Events
    // declare indexers
    // declare methods 
    // declare properties
}

//Syntax for implementing

class class_name : interface_name

//Example
interface inter1 
{ 
    // method having only declaration  
    // not definition 
    void display(); 
} 
  
// A class that implements interface. 
class testClass : inter1 
{ 
      
    // providing the body part of function 
    public void display() 
    { 
        Console.WriteLine("Sudo Placement Class"); 
    } 
  
    // Main Method 
    public static void Main (String []args) 
    { 
          
        // Creating object 
        testClass t = new testClass(); 
          
        // calling method 
        t.display(); 
    } 
} 
```


# What is the difference between constant and readonly?

Constants:

1.Constants are dealt with at compile-time.

2.Constants supports value-type variables.

3.Constants should be used when it is very unlikely that the value will ever change(example Pi value).

Read-only:

1.Read-only variables are evaluated at runtime.

2.Read-only variables can hold reference type variables.

3.Read-only variables should be used when run-time calculation is required.


# What is the difference between ref and out keywords?

| Ref | Out |
|---- | ----|
|The parameter or argument must be initialization first before it is passed to ref    | It is compulsory to initialize a parameter or argument before it is passed to an out |
|A called method is required to assign or initialize a value of a parameter (which is passed to an out)before returning to the calling method|It is not required to assign or initialize the value of a parameter(which is passed by ref ) before returning to the calling method|
|Passing a parameter value by ref is useful when the called method is also needed to modify the pass parameter|Declaring a parameter to an out method is when multiple values need to be returned for function or method|
|A parameter value must be initialized within calling method before its use|It is not compulsory to initialize a parameter value before using it in a calling method|
|When we use ref data can be passed bidirectionally|When we use out data is passed only in unidirectional way (from the called method caller )|


# Can we use “this” within a static method?

We can't use this in static method because keyword 'this' returns a reference to the current instance of the class containing it.

Static methods (or any static member) do not belong to a particular instance. They exist without creating an instance of the class and call with the name of a class not by instance so we can’t use this keyword in the body of static Methods, but in case of Extension Methods we can use it the functions parameters. Let’s have a look on “this” keyword.

The "this" keyword is a special type of reference variable that is implicitly defined within each constructor and non-static method as a first parameter of the type class in which it is defined. For example, consider the following class written in C#.




