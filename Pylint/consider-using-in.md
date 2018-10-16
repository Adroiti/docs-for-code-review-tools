Pattern: Missing use of `in (...)`

Issue: -

## Description

To check if a variable is equal to one of many values, combine the values into a tuple and check if the variable is contained `in` it instead of checking for equality against each of the values. This is faster and less verbose.
 
Example of **incorrect** code:

```python
name == 'a' or name == 'b' or name == 'c'
```

Example of **correct** code:

```python
name in ('a', 'b', 'c')
```
