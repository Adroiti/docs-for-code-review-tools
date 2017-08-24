Pattern: Overlapping data in `s[n]printf()`

Issue: -

## Description

The variable is used both as a parameter and as destination in `s[n]printf()`. The origin and destination buffers overlap. From glibc (C-library) documentation:

> If copying takes place between objects that overlap as a result of a call to `sprintf()` or `snprintf()`, the results are undefined.

## Further Reading

* [Common Weakness Enumeration (CWE) - 628](https://cwe.mitre.org/data/definitions/628.html)
* [The GNU C Library - 12.12.7 Formatted Output Functions](http://www.gnu.org/software/libc/manual/html_mono/libc.html#Formatted-Output-Functions)