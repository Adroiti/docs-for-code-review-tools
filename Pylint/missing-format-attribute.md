Pattern: Missing format attribute

Issue: -

## Description

Used when a _PEP 3101_ format string uses an attribute specifier, but the argument passed for formatting doesn't have that attribute. This message can't be emitted when using Python < 2.7.


Example of **incorrect** code:

```python
file = open('out.txt', 'w')
"My name is {0.unknown}".format(file) # file type does not have 'unknown'
```

Examples of **correct** code:

```python
file = open('out.txt', 'w')
"My name is {0.name}".format(file)
```

## Further Reading

* [Python Developer's Guide - Advanced String Formatting](https://www.python.org/dev/peps/pep-3101)
