Pattern: Missing use of dict comprehension

Issue: -

## Description

Although there is nothing syntactically wrong with this code, it is hard to read and can be simplified to a dict comprehension. Also it is faster since you don't need to create another transient list.

## Further Reading

* [PEP 274 -- Dict Comprehensions](https://www.python.org/dev/peps/pep-0274)
