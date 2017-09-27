Pattern: Unnecessary parentheses for method call

Issue: -

## Description

If a method is called and the only parameter to that method is an inline closure then the parentheses of the method call can be omitted.

Example of violations:

``` groovy
[1,2,3].each() { println it }
```

## Further Reading

* [CodeNarc - UnnecessaryParenthesesForMethodCallWithClosure](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryParenthesesForMethodCallWithClosure)