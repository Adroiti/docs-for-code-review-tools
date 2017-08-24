Pattern: Irregular whitespace

Issue: -

## Description

This rule enforces whitespace usage around an operator, bracket or block opener based on _PEP 8_ style guide. Warning is raised when any of the following rules is violated:
- Any of the following operators is surrounded by one space: `==, !=, <>, <=, >=, <, >, =, +=, -=, *=, **=, /=, //=, &=, |=, ^=, %=, >>=, <<=`
- Any opening bracket ( `(, [, {` ) is not followed by any space.
- Any closing bracket ( `), ], }` ) is not preceded by any space.
- Any comma is not preceded by any space, and is followed by one space.
- Any block opener colon is not preceded by any space.


Example of **incorrect** code:

```python
if x == 4 : print x , y ; x , y = y , x
```

Example of **correct** code:

```python
if x == 4: print x, y; x, y = y, x
```

The guidelines provided by _PEP 8_ are intended to improve the readability of code and make it consistent across the wide spectrum of Python code.

## Further Reading

* [PEP 8 - Whitespace in Expressions and Statements](https://www.python.org/dev/peps/pep-0008/#whitespace-in-expressions-and-statements)
* [Pylint - C0326](http://pylint-messages.wikidot.com/messages:c0326)
