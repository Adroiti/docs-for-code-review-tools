Pattern: Use `cls` as first agument of classmethod

Issue: -

## Description

The first argument of a class method is a reference to the current class. It is usually called `cls`. The `cls` name is used to easily differentiate class methods from instance methods.


Example of **incorrect** code:

```python
    def from_httplib(ResponseCls, r, **response_kw):
```

Example of **correct** code:

```python
    def from_httplib(cls, r, **response_kw):
```

## Further Reading

* [PEP 8 - Function and method arguments](http://legacy.python.org/dev/peps/pep-0008/#function-and-method-arguments)
