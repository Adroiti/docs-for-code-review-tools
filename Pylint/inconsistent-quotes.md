Pattern: Inconsistent qoute delimiter

Issue: -

## Description

Emitted when quotes delimiters (`"` and `'`) are not used consistently throughout a module.  It allows avoiding unnecessary escaping, allowing, for example, `"Don't error"` in a module in which single-quotes otherwise delimit strings so that the single quote in `Don't` doesn't need to be escaped.

Example of **incorrect** code:

```python
"""Tests for inconsistent quoting strategy.

Here double quotes are the majority quote delimiter.
"""

FIRST_STRING = "double-quoted string"
SECOND_STRING = 'single-quoted string' # [inconsistent-quotes]
THIRD_STRING = "another double-quoted string"
```

Example of **correct** code:

```python
"""Tests for inconsistent quoting strategy.

Here double quotes are the majority quote delimiter.
"""

FIRST_STRING = "double-quoted string"
SECOND_STRING = "now double-quoted string"
THIRD_STRING = "another double-quoted string"
```