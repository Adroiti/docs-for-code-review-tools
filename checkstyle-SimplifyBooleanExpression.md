Pattern: Overly complicated boolean expressions

Issue: -

## Description

Checks for over-complicated boolean expressions. Currently finds code like ` if (b == true)`, `b || true`, `!false`, etc. 

Rationale: Complex boolean logic makes code hard to understand and maintain. 

## Examples

To configure the check: 
    
    
    <module name="SimplifyBooleanExpression"/>

## Further Reading

* [checkstyle - SimplifyBooleanExpression](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanExpression)