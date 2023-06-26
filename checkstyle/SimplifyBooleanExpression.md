Pattern: Use of verbose boolean expression

Issue: -

## Description

Checks for over-complicated boolean expressions. Currently finds code like `if (b == true)`, `b || true`, `!false`, etc. 

Rationale: Complex boolean logic makes code hard to understand and maintain. 

## Examples

To configure the check: 


```xml
<module name="SimplifyBooleanExpression"/>
```

## Further Reading

* [checkstyle - SimplifyBooleanExpression](https://checkstyle.sourceforge.io/checks/coding/simplifybooleanexpression.html#SimplifyBooleanExpression)
