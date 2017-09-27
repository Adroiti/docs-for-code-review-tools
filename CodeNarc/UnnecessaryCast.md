Pattern: Unnecessary cast

Issue: -

## Description

Checks for unnecessary cast operations.

Example of violations:

``` groovy
int count = (int)123                    // violation
def longValue = (long)123456L           // violation
def bigDecimal = (BigDecimal)1234.56    // violation
String name = (String) "Joe"            // violation
def list = (List)[1, 2, 3]              // violation
def map = (Map)[a:1]                    // violation
```

## Further Reading

* [CodeNarc - UnnecessaryCast](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryCast)