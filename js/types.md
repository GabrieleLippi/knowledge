JavaScript has 7 types:
  * null
  * undefined
  * boolean
  * number
  * string
  * object
  * symbol

All of these except object are called "primitives".

We can check the type of a given value with **typeof** operator. Fun fact: `typeof null === 'null' // false typeof null === 'object' // true`. This original bug persist so long that is now impossible to fix it, because too many softwares are built on top of it.
For checkin null value we need a compound condition like this:
```var a = null 
(!a && typeof a === 'object')```

Functions are a subtype of objects. They are objects with a [[Call]] property.  

# In JavaScript variables doesn't have types, values have types.
This means that the engine doesn't insist that a variable always hold values of the same initial type that it starts it out with.
If we try to access a variable that is not defined , we get back an `undefined` error, same if we try to access a variable that it's never been declared, even if in this case it's `undeclared` and not `undefined`.
Anyway, if we chekf `typeof a` where `a` is undeclared or undefined we always get back `undefined`.
