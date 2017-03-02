Pattern: Unbalanced tuple unpacking

Issue: -

## Description

Used when there is an unbalanced tuple unpacking in assignment. Sequence unpacking requires the list of variables on the left to have the same number of elements as the length of the sequence.


Example of **incorrect** code:

```python
def do_stuff():
    first, second = 1, 2, 3 # last tuple value has no matching element
    return first + second
```

Example of **correct** code:

```python
def do_stuff():
    first, second = 1, 2
    return first + second
```

## Further Reading

* [The Python Tutorial - Tuples and Sequences](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences)
