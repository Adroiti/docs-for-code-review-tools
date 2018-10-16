Pattern: Invalid default for environment variable function

Issue: -

## Description

Environment variable manipulation functions return `None` or `str` values. Supplying anything different as a default may cause bugs.

## Further Reading

* [The Python Standard Library - Miscellaneous operating system interfaces](https://docs.python.org/3/library/os.html#os.getenv)