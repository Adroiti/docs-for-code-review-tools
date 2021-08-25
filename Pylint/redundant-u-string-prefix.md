Pattern: Use of `u` string prefix

Issue: -

## Description

Used when we detect a string with a `u` prefix. These prefixes were necessary in Python 2 to indicate a string was Unicode, but since Python 3.0 strings are Unicode by default.
