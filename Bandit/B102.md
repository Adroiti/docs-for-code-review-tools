Pattern: Avoid using `exec()` when possible

Issue: -

## Description

The `exec()` statement is dangerous, hard to test, and hard to read. Avoid it, as much as possible. This is largely due to the fact that `exec()` enables you to dynamically execute arbitrary Python code which is stored in literal strings. Consider going back to the code to check if there is a clearer, more direct way to accomplish the task.


Example of **insecure** code:

```python
text = "print \"suspicious code\""
exec text
```

Example of **secure** code:

```python
def foo():
    print "suspicious code"
    
foo()
```

## Further Reading

* [The Python Standard Library - exec()](https://docs.python.org/3/library/functions.html#exec)
* [OpenStack - B102: exec_used](https://docs.openstack.org/developer/bandit/plugins/exec_used.html)
