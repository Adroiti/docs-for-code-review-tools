Pattern: Avoid redefining built-ins

Issue: -

## Description

Used when a variable or function overrides a built-in. Overloading function names can make code hard to maintain and hard to read, and can cause subtle bugs when the wrong function is called.

Try to rename user-defined function to to a name that is not a built-in function.

## Further Reading

* [The Python Standard Library - Built-in Functions](https://docs.python.org/2/library/functions.html)
