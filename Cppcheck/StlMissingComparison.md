Pattern: Stl missing comparison

Issue: -

## Description

The iterator incrementing is suspicious - it is incremented at line  and then at line . The loop might unintentionally skip an element in the container. There is no comparison between these increments to prevent that the iterator is incremented beyond the end.

## Further Reading

* [Common Weakness Enumeration (CWE) - 834](https://cwe.mitre.org/data/definitions/834.html)