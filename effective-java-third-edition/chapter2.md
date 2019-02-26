# Chapter 2. Creating and Destroying Objects

## Item 1: Consider static factory methods instead of constructors
the traditional way for a class to allow the client to obtain an instance is to provide public constructor.
Another possibility is to provide *public static factory method*, which is a
simple static method that returns an instance of the class.
Pros:
unlike constructors
  * they have name
  * they're not required to create a new object each time they're invoked
  * they can return an object of any subtype of their return type
  * the class of the returned object can vary from call to call as a function
    of the input parameters
    parameters in a function
  * the class of the returned object need not to exist when the class
    containing the method is written
Cons:
  * classes without public or protected constructors cannot be subclassed
  * they are hard for programmers to find
