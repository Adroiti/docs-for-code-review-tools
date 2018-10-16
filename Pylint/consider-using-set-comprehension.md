Pattern: Missing use of set comprehension

Issue: -

## Description

Although there is nothing syntactically wrong with this code, it is hard to read and can be simplified to a set comprehension. Also it is faster since you don't need to create another transient list.

## Further Reading

* [The Python Standard Library - List Comprehensions](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions)
