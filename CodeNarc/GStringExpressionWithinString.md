Pattern: GString expression within string

Issue: -

## Description

Checks for regular (single quote) strings containing a GString-type expression (`$<span id="a..">..</span>`).

Example of violations:

``` groovy
def str1 = 'total: ${count}'                // violation
def str2 = 'average: ${total / count}'      // violation

def str3 = "abc ${count}"                   // ok; GString
def str4 = '$123'                           // ok
def str5 = 'abc {123}'                      // ok
```

## Further Reading

* [CodeNarc - GStringExpressionWithinString](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#gstringexpressionwithinstring-rule)