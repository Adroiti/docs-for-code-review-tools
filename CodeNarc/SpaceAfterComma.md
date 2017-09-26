Pattern: Malformed space after `,`

Issue: -

## Description

Checks that there is at least one space or whitespace following each comma. That includes checks for method and closure declaration parameter lists, method call parameter lists, Map literals and List literals.

Known limitations:

-   May not catch actual violations if the source line contains unicode character literals, e.g. `'\u00A0'`

Examples of violations:

``` groovy
def value = calculate(1,399, 'abc')         // violation on parameter 399

def method1(int a,String b) { }             // violation on parameter b

def closure1 = { int a,String b -> }        // violation on parameter b

def list1 = [a,b, c]                        // violation on list element b

def map1 = [a:1,b:2, c:3]                   // violation on map element b:2
```

## Further Reading

* [CodeNarc - SpaceAfterComma](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterComma)