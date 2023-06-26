Pattern: Too many conditions in boolean expression

Issue: -

## Description

Restrict the number of `&&`, `||`, `&`, `|` and `^` in an expression. 

Rationale: Too many conditions leads to code that is difficult to read and hence debug and maintain. 

Note that the operators `&` and `|` are not only integer bitwise operators, they are also the [non-shortcut versions](http://docs.oracle.com/javase/specs/jls/se8/html/jls-15.html#jls-15.22.2) of the boolean operators. `&&` and `||`. 

Note that `&`, `|` and `^` are not checked if they are part of constructor or method call because they can be applied to non boolean variables and Checkstyle does not know types of methods from different classes. 

## Examples

To configure the check: 


```xml
<module name="BooleanExpressionComplexity"/>
```
        

To configure the check with 7 allowed operation in boolean expression: 


```xml
<module name="BooleanExpressionComplexity">
    <property name="max" value="7"/>
</module>
```
        

To configure the check to ignore `&` and `|`: 


```xml
<module name="BooleanExpressionComplexity">
    <property name="tokens" value="BXOR,LAND,LOR"/>
</module>
```

## Further Reading

* [checkstyle - BooleanExpressionComplexity](https://checkstyle.sourceforge.io/checks/metrics/booleanexpressioncomplexity.html#BooleanExpressionComplexity)
