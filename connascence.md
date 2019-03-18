# Connascence

## NAME:

    is unavoidable, since we refer to entities using labels
    is the weakest connascence

if we change the name of an entity when we declare it,
we must also change all code that refers to that entity

## TYPE:
    for statically tiped language, is not a big issue
    for dynamic languages, like Python, JavaScript etc, could raise some issues
multiple components must agree on the type of an entity

## MEANING:
consider this code:
```python
    def is_credit_card_number_valid(card_number):
        # Check for 'test' credit card numbers:
        if card_number == "9999-9999-9999-9999":
            return True
        # Do normal validation:
```
all parts of this system must agree that,
```9999-9999-9999-9999``` is the test credit card number.

often meaning issues could be solved with connascence of name,
extracting "magic values" to named constants

A more common and insidious example of connascence of meaning
is agreeing on the meaning of null values.

Fortunately, there are things we can do to reduce connascence of meaning
into connascence of type,avoiding "Primitive Obsession", and connascence of name.
