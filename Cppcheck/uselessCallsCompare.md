Pattern: Inefficient `string::find()` call

Issue: -

## Description

It is inefficient to call `string::find()` as it always returns 0.

## Further Reading

* [Common Weakness Enumeration (CWE) - 628](https://cwe.mitre.org/data/definitions/628.html)