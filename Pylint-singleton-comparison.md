Pattern: Use `is` or `is not` for singleton comparison

Issue: -

## Description

This rule enforces `PEP 8` recommendation to use `is` or `is not` over equality operators for singleton comparison. 


Example of **incorrect** code:

```python
number = None

if number == None:
    print "number is None"
```

Example of **correct** code:


```python
number = None

if number is None:
    print "number is None"
```

## Further Reading

* [PEP 8 - Programming Recommendations](https://www.python.org/dev/peps/pep-0008/#programming-recommendations)
