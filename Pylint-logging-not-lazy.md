Pattern: Logging not lazy

Issue: -

## Description

Used when a logging statement has a call form of `logging.<logging method>(format_string % (format_args...))`. Such calls should leave string interpolation to the logging method itself and be written `logging.<logging method>(format_string, format_args...)` so that the program may avoid incurring the cost of the interpolation in those cases in which no message will be logged.

## Further Reading

* [ Python Developer's Guide - A Logging System](http://www.python.org/dev/peps/pep-0282)
