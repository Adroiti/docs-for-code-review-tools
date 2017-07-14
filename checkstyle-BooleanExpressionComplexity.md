Pattern: Restrict nested boolean operators (&amp;&amp;, ||, &amp;, | and ^) to a specified depth

Issue: -

## Description

Restrict the number of number of `&&`, `||`, `&`, `|` and `^` in an expression. 

Rationale: Too many conditions leads to code that is difficult to read and hence debug and maintain. 

Note that the operators `&` and `|` are not only integer bitwise operators, they are also the [ non-shortcut versions](http://docs.oracle.com/javase/specs/jls/se8/html/jls-15.html#jls-15.22.2) of the boolean operators. `&&` and `||`. 

Note that `&`, `|` and `^` are not checked if they are part of constructor or method call because they can be applied to non boolean variables and Checkstyle does not know types of methods from different classes. 

## Examples

To configure the check: 
    
    
    <module name="BooleanExpressionComplexity"/>
            

To configure the check with 7 allowed operation in boolean expression: 
    
    
    <module name="BooleanExpressionComplexity">
        <property name="max" value="7"/>
    </module>
            

To configure the check to ignore `&` and `|`: 
    
    
    <module name="BooleanExpressionComplexity">
        <property name="tokens" value="BXOR,LAND,LOR"/>
    </module>

## Further Reading

* [checkstyle - BooleanExpressionComplexity](http://checkstyle.sourceforge.net/config_metrics.html#BooleanExpressionComplexity)