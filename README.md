# C-sharp-interview-question
Updated C Sharp(C#) interview questions list

| No. | Questions |
|---- | ---------|
|1    | [What is C#(C Sharp)?	](#what-is-c )|
|2    | [What is an Object?	](#what-is-an-object )|
|3    | [What is the difference between a struct and a class in C#?	](#what-is-the-difference-between-a-struct-and-a-class-in-c )|
|4    | [What is the difference between Interface and Abstract Class?	](#what-is-the-difference-between-interface-and-abstract-class )|
|5    | [What is the difference between constant and readonly?	](#what-is-the-difference-between-constant-and-readonly )|
|7    | [What is the difference between ref and out keywords?	](#what-is-the-difference-between-ref-and-out-keywords )|
|8    | [Can we use “this” within a static method?	](#can-we-use-this-within-a-static-method )|
|9    | [What is the difference between string and StringBuilder in C#?	](#what-is-the-difference-between-string-and-stringbuilder-in-c )|
|10   | [What are sealed class?	](#what-are-sealed-class )|
|11   | [What are partial classes?	](#what-are-partial-classes )|
|12   | [What is difference between late binding and early binding?	](#what-is-difference-between-late-binding-and-early-binding )|
|13   | [What is dependecny injection(DI)?	](#what-is-dependecny-injectiondi )|
|14   | [Explain SOLID priciples in detail	](#explain-solid-priciples-in-detail )|
|15   | [Differences between IEnumerable and IQueryable in C# ](Differences between IEnumerable and IQueryable in C#?)|
|16   | [Async and Await in C#](What is a Delegate in C#?)|
|17   | [What is a Delegate in C#?	](#What is a Delegate in C#? )|


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


# What is the difference between string and StringBuilder in C#?

|string|StringBuilder|
|----|----|
|It’s an immutable object that holds string value.|StringBuilder is a mutable object.|
|Performance wise string is slow because its’ create a new instance to override or change the previous value.|Performance wise StringBuilder is very fast because it will use same instance of StringBuilder object to perform any operation like insert value in existing string.|
| String belongs to System namespace.|StringBuilder belongs to System.Text.Stringbuilder namespace.|


# What are sealed class?

Sealed classes are used to restrict the inheritance feature of object oriented programming. Once a class is defined as a sealed class, the class cannot be inherited.

In C#, the sealed modifier is used to define a class as sealed. In Visual Basic .NET the Not Inheritable keyword serves the purpose of sealed. If a class is derived from a sealed class then the compiler throws an error.

If you have ever noticed, structs are sealed. You cannot derive a class from a struct.

The following class definition defines a sealed class in C#:



## Example:

```csharp
Sealed class sealed class SealedClass { }
```

# What are partial classes?

A partial class is only use to splits the definition of a class in two or more classes in a same source code file or more than one source files. You can create a class definition in multiple files but it will be compiled as one class at run time and also when you’ll create an instance of this class so you can access all the methods from all source file with a same object.

Partial Classes can be created in the same namespace it’s not allowed to create a partial class in different namespace. So use “partial” keyword with the entire class name in which you want to bind together with the same name of class in same namespace



## Example:

```csharp
public partial class Test {
	private string Author_name;
	private int Total_articles;

	public Test(string a, int t)
	{
		this.Authour_name = a;
		this.Total_articles = t;
	}
}

```


# What is difference between late binding and early binding?

Early Binding and Late Binding concepts belongs to polymorphism so let’s see first about polymorphism: Polymorphism is an ability to take more than one form of a function means with a same name we can write multiple functions code in a same class or any derived class.

Polymorphism we have 2 different types to achieve that: • Compile Time also known as Early Binding or Overloading. • Run Time also known as Late Binding or Overriding.

Compile Time Polymorphism or Early Binding: In Compile time polymorphism or Early Binding we will use multiple methods with same name but different type of parameter or may be the number or parameter because of this we can perform different-different tasks with same method name in the same class which is also known as Method overloading.

# What is dependecny injection(DI)?

Explaination 1(In Simple Words):

Dependency Injection can exist between two objects, for instance, a flashlight and a battery. The flashlight needs the battery to function. However, any changes made to the battery, such as switching it with another brand/set of batteries, does not mean the dependent object (flashlight) also needs to be changed.

Such code is called a tighlty coupled code, DI gives us the freedom of writing decoupled code.

Explaination 2(In Technical Words):

Dependency injection (DI) is a software design pattern that allows us to separate the dependencies of a class from its implementation.


# Explain SOLID priciples in detail

• First introduced by Robin C Martin.

• Five priciples of object-oriented class design 

• Set of rules and best practices to follow while designing a class structure.

S: Single Responsibility Principle (SRP)

O: Open-closed Principle (OCP)

L: Liskov substitution Principle (LSP)

I: Interface Segregation Principle (ISP)

D: Dependency Inversion Principle (DIP)

S- Single Responsibility Principle (SRP): Every software module or class should have only one reason to change. we can say that each module or class should have only one responsibility.

O: Open-closed Principle (OCP): The Open-Closed Principle states that software entities such as modules, classes, functions, etc., should be open for extension but closed for modification.

L: Liskov substitution Principle (LSP): The Liskov Substitution Principle states that the object of a derived class should be able to replace an object of the base class without bringing any errors in the system or modifying the behavior of the base class. That means the child class objects should be able to replace parent class objects without changing the correctness or behavior of the program.

I: Interface Segregation Principle (ISP): The Interface Segregation Principle states that Clients should not be forced to implement any methods they don’t use. Rather than one fat interface, numerous little interfaces are preferred based on groups of methods, with each interface serving one submodule.

D: Dependency Inversion Principle (DIP): The Dependency Inversion Principle (DIP) states that high-level modules/classes should not depend on low-level modules/classes. Both should depend upon abstractions. Secondly, abstractions should not depend upon details. Details should depend upon abstraction.

# Differences between IEnumerable and IQueryable in C#?

|IEnumerable| IQueryable|
|----|----|
|IEnumerable exists in the System.Collections namespace.|
|IQueryable exists in the System.Linq Namespace.|
| IEnumerable is suitable for querying data from in-memory collections like List, Array and so on.|IQueryable is suitable for querying data from out-memory (like remote database, service) collections.|
|While querying data from the database, IEnumerable executes "select query" on the server-side, loads data in-memory on the client-side and then filters the data.|While querying data from a database, IQueryable executes a "select query" on server-side with all filters.|
|IEnumerable is beneficial for LINQ to Object and LINQ to XML queries.|IQueryable is beneficial for LINQ to SQL queries.|











