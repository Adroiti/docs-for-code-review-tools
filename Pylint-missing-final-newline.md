Pattern: Missing final newline

Issue: -

## Description

Used when the last line in a file is missing a newline. While Python interpreters typically do not require line end character(s) on the last line, other programs processing Python source files may do, and it is simply good practice to have it.


Example of **incorrect** code:

```python
"""This file does not have a final newline."""
from __future__ import print_function
# +1:[missing-final-newline]
print(1)
```

This would result in  **correct** code if newline is added after `print(1)`.


## Further Reading

* [Pylint - C0304](http://pylint-messages.wikidot.com/messages:c0304)
