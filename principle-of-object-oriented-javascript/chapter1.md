# Primitive and reference types

in JS we have two kinds of types: *primitive* and *reference*.
primitive types => stored as simple data types
reference types => stored as object

**the tricky part is that JS lets you treat primitive types like reference types
in order to make the language more consistent for the developer**

**JS tracks variable for a particular scope with a *variable object***
Primitive values are stored directly on the variable object, reference values
are placed as a pointer in the variable object

### primitive types
  1 Boolean
  2 Number
  3 String
  4 Null
  5 Undefined

variables holding a primitive directly contains the primitive value, rather than
a pointer to an object

**the best way to identify primitive types is with the *typeof* operator**
the tricky part involves null
```js
console.log(typeof null);    // "object"
```
for this reason, the best way to determine if a value is null, is to compare it
against null directly
```js
console.log(typeof value === null);    // true or false
```

**Despite the fact that they have methods, primitive values themselves are not objects.
JavaScript makes them look like objects to provide a consistent experience in the
language**

### reference types
reference types represent object in JS and are the closest thing to classes
**an object is an unordered list of properties consisting of a name and a value**
when the value of a property is a function, it's called a *method*
**function themselves are actually reference values in JS, so there isn't a lot
of difference between a property that contains an array and another that
contains a function, except that this second one can be executed**

it could help sometimes to think of JS object as hash tables

there are a couple of way to instatiate objects in JS, the first is to use the *new*
operator with a constructor. A constructor is simply a function that uses new to
create an object. By convention, constructor function starts with the first
letter capitalized to distinguish them from nonconstructor functions.
```js
var object = new Object();
```
**Reference types do not store the object directly into the variable to which it is assigned,
so the object variable in this example doesn’t actually contain the object instance.
Instead, it holds a pointer (or reference) to the location in memory where the object exists.
This is the primary difference between objects and primitive values, as the primitive
is stored directly in the variable.**

JS is a **garbage-collected language**, so you don’t need to worry about memory allocations.
However, it’s best to **dereference objects that you no longer need** so that the garbage
collector can free up that memory. The best way to do this is to set the object variable to null
