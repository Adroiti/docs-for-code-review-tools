Pattern: Avoid using wildcard (*) imports

Issue: -

## Description

Wildcard imports (`from <module> import *`) should be avoided, as they make it unclear which names are present in the namespace, confusing both readers and many automated tools. Although certain modules are designed to export only names that follow certain patterns when you use `import *`, it is still considered bad practice in production code.

Make the import statement more specific or import the whole module depending on your needs.


Example of **incorrect** code:
```python
from math import *  # [wildcard-import]

result = math.trunc(123.45)
```

Example of **correct** code:
```python
from math import trunc

result = math.trunc(123.45)
```

## Further Reading

* [The Python Tutorial - Importing * From a Package](https://docs.python.org/3/tutorial/modules.html#importing-from-a-package)
* [PEP 8 - Imports](https://www.python.org/dev/peps/pep-0008/#imports)
