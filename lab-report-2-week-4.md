Failure Inducing Input, Bugs, and Symptoms on Markdown Parse
===================================

Note: Our group only had one main commit that fixed bugs in the original code. Therefore, this is the only code change that will be shown here.

Code Change Difference
-----------------

![Image](code_diff.png)

Failure Inducing Input
--------------------

[Here](https://github.com/alien-traveler/markdown-parse/blob/main/test3.md) is a test file for which the original code would fail.

![Image](exception.png)

Relationship between Failure Inducing Input, Bugs, and Symptoms
----------

The failure-inducing input contains no brackets or links, so the original program would be unable to find them and thus throw an exception as shown above, which is a symptom. The underlying bug was the fact that the program looked for brackets via `indexOf()` and then used the values it got regardless of whether brackets were actually present, leading to an `IndexOutOfBounds` exception.
