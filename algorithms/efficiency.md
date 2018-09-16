Efficiency is the way to measure the qaulity of an algorithm. Efficiency is basically the ratio between **space** and **time**.
The big O notation is the standard way to measure efficiency.
It's expressed as O(n), where **n** is a mathematical expression.
**n** represents the length of the input of the function.
If we have a simple function like this (pseudo-code):

function decode(input):
 create output_string
  for each letter in input
    get new_letter from letter's location in cipher
    add new_letter to output
  return output

we can translate in big O notation as O(2n + 2), since create an output string and return it need to be run only once, instead of the for loop that need to be run for each letter in the input string.
If our input string have a lenght of 10, big O notation would look something like: 2(10) + 2, that is 22.
###to get the actual efficiency we can multiply the value 22 times the amount of time it takes to computer to run one line of code.

Reconsidering the previous notation, we have to consider that since the for loop need itself a computation in order to retrieve the letter each time, the notation should look like O(3n + 2).
Furthermore, we also need to consider the data structure that contains the letters, if it's a list, for example, we need to check each letter against the others, and this means 26 checks for each letter.
In the end, our big O notation for the simple function above, could look like this: O((3 +26)n + 2), so O(29n + 2).

When it comes to estimate time, it's always a matter of **approximation**.
Generally, we consider always the **best case scenario**, the **average case scenario** and the **worst case scenario**.
