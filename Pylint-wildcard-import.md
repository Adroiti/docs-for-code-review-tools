Pattern: Disallow wildcard import

Issue: -

## Description

Wildcard imports `( from <module> import * )` should be avoided, as they make it unclear which names are present in the namespace, confusing both readers and many automated tools. 

There is one defensible use case for a wildcard import, which is to republish an internal interface as part of a public API (for example, overwriting a pure Python implementation of an interface with the definitions from an optional accelerator module and exactly which definitions will be overwritten isn't known in advance).

## Further Reading

* [The Python Tutorial - Importing * From a Package](https://docs.python.org/3/tutorial/modules.html#importing-from-a-package)
* [PEP 8 - Imports](https://www.python.org/dev/peps/pep-0008/#imports)
