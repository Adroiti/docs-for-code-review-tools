Pattern: Function const

Issue: -

## Description

The member function `class::function` can be made a const function. Making this function `const` should not cause compiler errors. Even though the function can be made const function technically it may not make sense conceptually. Think about your design and the task of the function first - is it a function that must not change object internal state?

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)