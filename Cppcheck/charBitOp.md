Pattern: Char bit op

Issue: -

## Description

When using `char` variables in bit operations, sign extension can generate unexpected results. For example:
    char c = 0x80;
    int i = 0 | c;
    if (i & 0x8000)
        printf("not expected");
The "not expected" will be printed on the screen.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)