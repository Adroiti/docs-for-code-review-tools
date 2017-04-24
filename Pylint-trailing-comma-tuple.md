Pattern: Disallow trailing comma tuple

Issue: -

## Description

In Python, a tuple is actually created by the comma symbol, not by the parentheses. 
Unfortunately, one can actually create a tuple by misplacing a trailing comma, which can lead to potential weird bugs in your code. 
You should always use parentheses explicitly for creating a tuple


Example of **incorrect** code:

```python
tuple_test = 1, 2,
```

Example of **correct** code:

```python
tuple_test = (1, 2)
```
