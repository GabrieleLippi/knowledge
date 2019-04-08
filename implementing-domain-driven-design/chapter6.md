# Value Objects
>just an unharmed and harmless Value that comes and goes as needed

Value Objects are a vital building block of DDD, we should strive to model using
Value Objects instead of Entities whenever is possible, because they're are easy
to create, test, use and optimize. A Value can have a brief or long existence.

When you are trying to decide whether a concept is a Value, you should
determine whether it possesses most of these characteristics:
* It measures, quantifies, or describes a thing in the domain.
* It can be maintained as immutable.
* It models a conceptual whole by composing related attributes as an integral unit.
* It is completely replaceable when the measurement or description changes.
* **It can be compared with others using Value equality**.
* It supplies its collaborators with Side-Effect-Free Behavior.

A Value Object is not a thing in your domain; it's actually a **concept** that
measures, quantifies, or otherwise **describes a thing in the domain**.

### A conceptual whole
A Value Object may possess just one, a few, or a number of individual attributes,
each of which is related to the others. Each attribute contributes an
important part to a whole that collectively the attributes describe. Taken apart
from the others, each of the attributes fails to provide a cohesive meaning.

### Value Objects and CQS
Bertrand Meyer described Side-Effect-Free Functions as the Query methods
of his Command-Query Separation principle, or CQS, as discussed by Martin
Fowler. A query method is one that asks an object a question.
By definition, asking an object a question must not change the answer.

### Everything as Value Object
By now you may have begun to think that everything looks like a Value Object.
That’s better than thinking that everything looks like an Entity.

### Martin Fowler [advice](https://martinfowler.com/bliki/ValueObject.html):
It's often a good idea to **replace common primitives**, such as strings, **with
appropriate value objects**.
While I can represent a telephone number as a string, turning into a telephone
number object makes variables and parameters more explicit (with type checking
when the language supports it), a natural focus for validation, and avoiding
inapplicable behaviors (such as doing arithmetic on integer id numbers).

## TL;DR
**When you care only about the attributes of an element of the model, classify it as
a VALUE OBJECT**.
**Treat the VALUE OBJECT as immutable**.
Don’t give it any identity and avoid the design complexities necessary to maintain ENTI-
TIES.
