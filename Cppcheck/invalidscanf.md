Pattern: Use of `scanf()` without field width

Issue: -

## Description

`scanf()` without field width limits can crash with huge input data. Add a field width specifier to fix this problem.

Sample program that can crash:

```cpp
#include <stdio.h>
int main()
{
    char c[5];
    scanf("%s", c);
    return 0;
}
```


Typing in 5 or more characters may make the program crash. The correct usage here is `scanf("%4s", c);`, as the maximum field width does not include the terminating null byte.

## Further Reading

* [Common Weakness Enumeration (CWE) - 119](https://cwe.mitre.org/data/definitions/119.html)