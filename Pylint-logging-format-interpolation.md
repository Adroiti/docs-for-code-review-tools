Pattern: Logging format interpolation

Issue: -

## Description

Used when a logging statement has a call form of `logging.<logging method>(format_string.format(format_args...))`. Such calls should use % formatting instead, but leave interpolation to the logging function by passing the parameters as arguments.

## Further Reading

* [Python Developer's Guide - A Logging System](http://www.python.org/dev/peps/pep-0282)
