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

* [CodeNarc - GStringExpressionWithinString](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#GStringExpressionWithinString)