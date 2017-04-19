Pattern: Avoid use of `assert` keyword

Issue: -

## Description

`assert` is removed with compiling to optimised byte code (`python -o` producing _*.pyo_ files). This causes various protections to be removed. It was discovered that some projects used assert to enforce interface constraints. The use of `assert` is also considered as general bad practice in OpenStack codebases.


Example of **incorrect** code:

```python
assert logged_in
display_assets()
```


Example of **correct** code:

```python
if logged_in:
  display_assets()
```

## Further Reading

* [The Python Language Reference - The assert statement](https://docs.python.org/2/reference/simple_stmts.html#the-assert-statement)
* [OpenStack - B101: assert_used](https://docs.openstack.org/developer/bandit/plugins/assert_used.html)
