Pattern: Use of insecure `mktemp()` function

Issue: -

## Description

Use of this function may introduce a security hole in your program. By the time you get around to doing anything with the file name it returns, someone else may have beaten you to the punch. Use `mkstemp()` instead or replace with with `NamedTemporaryFile()`, passing it the `delete=False `parameter.
 

Example of **incorrect** code:

```python
tempfile.mktemp('foo')
```

Example of **correct** code:

```python
tempfile.mkstemp('foo')
```
## Further Reading

* [The Python Standard Library - mktemp](https://docs.python.org/2/library/tempfile.html#tempfile.mktemp)
* [OpenStack - B306: mktemp_q](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b306-mktemp-q)
