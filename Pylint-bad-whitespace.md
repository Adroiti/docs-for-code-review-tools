Pattern: Bad whitespace

Issue: -

## Description

This rule enforces whitespace usage in expressions and statements based on `PEP 8` style guide. 

Example of **incorrect** code:

```python
if x == 4 : print x , y ; x , y = y , x
```

Example of **correct** code:

```python
if x == 4: print x, y; x, y = y, x
```

## Further Reading

* [PEP 8 - Whitespace in Expressions and Statements](https://www.python.org/dev/peps/pep-0008/#whitespace-in-expressions-and-statements)
