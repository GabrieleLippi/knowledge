Functional programming could mean:
* programming with function
* programming with pure functions
* function as **first class object**
  * high order functions
  * lexical closure

## Monad Axioms:

```
bind(unit(value), f) ==== f(value)

bind(monad, unit) ==== monad

bind(bind(monad, f), g) ==== bind(monad, (value) => bind(f(value), g))
```

## The OO transformation:

```
bind(monad, func)
```

into

```
monad.bind(func)
```

Functional programming becomes interesting when we are in the second case.

Lexical closure invented by Scheme

A monad generally it's an object

```js
function MONAD() {
  return function unit(value) {
    var monad = Object.create(null);
    monad.bind = function (func) {
      return func(value);
    }
    return monad;
  }
}
```

```js
var identity = MONAD();
var monad = identity("Hello World.");
monad.bind(alert);
```

Improving monad by adding capability to have more methods:
```js
function MONAD() {
  var prototype = Object.create(null);
  return function unit(value) {
    var monad = Object.create(prototype);
    monad.bind = function (func, args) {
      return func(value, ...args);
    }
    return monad;
  }
  return unit;
}
```
