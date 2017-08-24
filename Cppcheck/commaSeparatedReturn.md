Pattern: Comma used in return statement

Issue: -

## Description

Comma is used in return statement. When comma is used in a return statement it can easily be misread as a semicolon. For example in the code below the value of `b` is returned if the condition is true, but it is easy to think that `a+1` is returned:

```cpp
if (x)
	return a + 1,
b++;
```


However it can be useful to use comma in macros. Cppcheck does not warn when such a macro is then used in a return statement, it is less likely such code is misunderstood.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)