Pattern: Comparison to literal

Issue: -

## Description

Used when comparing an object to a literal, which is usually what you do not want to do, since you can end up comparing to a different literal than what was expected altogether.
Also note that `is` is for identity testing, `==` is for equality testing.


Example of **incorrect** code:

```python
if "test" is "code":
    pass
```

Both strings are actually stored in the same memory location, they have the same _identity_, so the `is` operator works as expected. But if you construct a string by some other method (even if that string contains _exactly_ the same characters), then the string may be _equal_, but it is not the _same string_ - that is, it has a different _identity_, because it is stored in a different place in memory.


Example of **correct** code:

```python
if "test" == "code":
    pass
```

## Further Reading

* [StackOverflow - Why does comparing strings in Python using either '==' or 'is' sometimes produce a different result?](http://stackoverflow.com/questions/1504717/why-does-comparing-strings-in-python-using-either-or-is-sometimes-produce)
