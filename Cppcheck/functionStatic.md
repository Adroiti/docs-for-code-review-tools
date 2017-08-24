Pattern: Non-static member function

Issue: -

## Description

Member function can be made static. Making a function static can bring a performance benefit since no `this` instance is passed to the function. This change should not cause compiler errors but it does not necessarily make sense conceptually. Think about your design and the task of the function first - is it a function that must not access members of class instances?

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)