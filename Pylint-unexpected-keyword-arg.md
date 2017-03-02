Pattern: Unexpected keyword argument in function call

Issue: -

## Description

Python will raise a `TypeError` at runtime if function definition does not expect keyword argument. Modify the function to support keyword arguments or pass the parameter as supported keyword or a positional parameter to resolve this issue.


Example of **incorrect** code:

```python
def calc_area(width):
    return width * 2

calc_area(height = 12)
```

Example of **correct** code:

```python
def calc_area(width):
    return width * 2

calc_area(width = 12) # passing expected keyword
calc_area(12) # passing positional parameter
```

## Further Reading

* [The Python Tutorial - Keyword Arguments](https://docs.python.org/2/tutorial/controlflow.html#keyword-arguments)
