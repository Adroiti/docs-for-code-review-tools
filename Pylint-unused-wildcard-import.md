Pattern: Unused wildcard import

Issue: -

## Description

Used when an imported module or variable is not used from a `'from X import *'` style import. Use or remove such code to resolve this issue.


Examples of **incorrect** code:
```python
from indirect1 import * # [wildcard-import]
# This is an unresolved import which still generates the wildcard-import warning.
from unknown.package import * # [wildcard-import]
```

In general, wildcard imports should be avoided, as they make it unclear which names are present in the namespace, confusing both readers and many automated tools. 

## Further Reading

* [The Python Tutorial - Importing * From a Package](https://docs.python.org/3/tutorial/modules.html#importing-from-a-package)
* [PEP 8 - Imports](https://www.python.org/dev/peps/pep-0008/#imports)
