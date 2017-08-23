Pattern: Assert with side effect

Issue: -

## Description

Non-pure function: `function` is called inside assert statement. Assert statements are removed from release builds so the code inside assert statement is not executed. If the code is needed also in release builds, this is a bug.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)