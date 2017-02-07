Pattern: Mixed indentation

Issue: -

## Description

Python interprets tabs and spaces differently, so consistent indentation is critical to the correct interpretation of blocks in Python syntax.

This warning is raised when a mix of both spaces and tabs is used in indentation or more precisely, when an indent is detected that is not consistent with the Pylint's `indent-string` option. By default, `indent-string` is set to four spaces.

## Further Reading

* [PEP 8 - Indentation](https://www.python.org/dev/peps/pep-0008/#indentation)
* [Pylint - W0312](http://pylint-messages.wikidot.com/messages:w0312)
