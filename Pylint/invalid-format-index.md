Pattern: Invalid format index

Issue: -

## Description

Used when a _PEP 3101_ format string uses a lookup specifier - `{a[1]}` - but the argument passed for formatting doesn't contain or doesn't have that key as an attribute. This message can't be emitted when using Python < 2.7.

## Further Reading

* [Python Developer's Guide - Advanced String Formatting](https://www.python.org/dev/peps/pep-3101)
