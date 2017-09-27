Pattern: Unnecessary boolean expression

Issue: -

## Description

Checks for unnecessary boolean expressions, including ANDing (`&&`) or ORing (`||`) with `true`, `false`, `null`, or a Map/List/String/Number literal.

This rule also checks for negation (`!`) of `true`, `false`, `null`, or a Map/List/String/Number literal.

Examples of violations include:

``` groovy
result = value && true              // AND or OR with boolean constants
if (false || value) { .. }
return value && Boolean.FALSE

result = null && value              // AND or OR with null

result = value && "abc"             // AND or OR with String literal

result = value && 123               // AND or OR with Number literal
result = 678.123 || true

result = value && [x, y]            // AND or OR with List literal

result = [a:123] && value           // AND or OR with Map literal

result = !true                      // Negation of boolean constants
result = !false
result = !Boolean.TRUE

result = !null                      // Negation of null

result = !"abc"                     // Negation of String literal

result = ![a:123]                   // Negation of Map literal

result = ![a,b]                     // Negation of List literal
```

## Further Reading

* [CodeNarc - UnnecessaryBooleanExpression](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryBooleanExpression)