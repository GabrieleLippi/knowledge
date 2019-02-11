# Degenerate Objects
The general TDD cycle goes as follows:

  1. Write a test
  2. Make it run
  3. Make it right

**The goal is *clean code*, but first we had to make it works**

Following are the strategies I know for quickly getting to green:

 1. Fake It - Return a constant and gradually replace constants with variables until you have the real code.
 2. Use Obvious Implementation - Type in the real implementation.
 3. Triangolation (see chapter 3)

The translation of a feeling (for example, disgust at side effects) into a test (for example, multiply the same Dollar twice) is a common theme of TDD.
The longer I do this, the better able I am to translate my aesthetic judgments into tests.
