# Connascence

## NAME:
* is unavoidable, since we refer to entities using labels
* is the weakest connascence

if we change the name of an entity when we declare it,
we must also change all code that refers to that entity

## TYPE:
* for statically tiped language, is not a big issue
* for dynamic languages, like Python, JavaScript etc, could raise some issues
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
`9999-9999-9999-9999` is the test credit card number.

```python
def get_user_role(username):
    user = database.get_user_object_for_username(username)
    if user.is_admin:
        return 2
    elif user.is_manager:
        return 1
    else:
        return 0
```
here you need to remember that `2` is the code associated with `admin` in all the place where you refer to it

A more common and insidious example of connascence of meaning
is agreeing on the meaning of null values.
```python
def find_user_in_database(username):
    try:
        return database.find_user(username=username) or None
    except DatabaseError:
        return None
```
here the meaning of `None` is ambigous

### possible workarounds - transform connascence of meaning into:
* connascence of name, by extracting "magic values" to named constants
* connascence of type, by extracting ambiguos primitives to custom type (avoid "Primitive Obsession")

## Resume Table
| connascence | avoidable |
|---|---|
| name | no |
| type | depends - dynamic/static typed language |
| meaning | yes |
