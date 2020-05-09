# Test-Driven Development with Objects

The chapter introduce the concept of **mocking** collaborators during the unit
test of class which need those collaborators.

## The Law of Demeter

They suggest to avoid doing nested calls to different methods of an object,
instead it should be prefered to call a public method in a **declarative** way
which should abstract away the details of what is going on under the hoods.
This introduce also the need of mocking in test, as you may find yourself
wanting to test some behaviour that happen outside the class under test.
