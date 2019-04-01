# 4 rules of simple design
>Martin Fowler, 2 March 2015 [BeckDesignRules](https://www.martinfowler.com/bliki/BeckDesignRules.html)

1 - passes tests
2 - reveals intention
3 - no duplication
4 - fewest elements

**the rules are in priority order**

The most important of the rules is "passes the tests"; the point is that whatever you do with software, the primary aim is that is work as itended and tests are there to ensure that happens.

"Reveals intention" is Kent Beck's way of saying that code should be easy to understand. Communication is a core value of Extreme Programming.

Many programmers have observed that the exercise of eliminating duplication is a powerful way to drive out good designs.

The last rule say that anything that doesn't serve the three prior rules should be removed.

People often to see tension between the second and third principle; Fowler disagree, reporting what Kent Beck said:
*"In the rare case they are in conflict (in tests are the only examples I can recall), empathy wins over some strictly technical metric."* I like his point about empathy - it reminds us that when writing code we should always be thinking of the reader.
