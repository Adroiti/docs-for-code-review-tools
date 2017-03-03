Pattern: Module is importing itself

Issue: -

## Description

A module should not import itself. So for example, if the module is named `test_import_self` you cannot import it as follows:


```python
import test_import_self
```

## Further Reading

* [The Python Tutorial - Modules](https://docs.python.org/2/tutorial/modules.html)
