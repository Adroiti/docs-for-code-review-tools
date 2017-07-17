Pattern: Prefer `equals()` over `==` or `!=` for literal strings

Issue: -

## Description

Checks that string literals are not used with `==` or `!=`. 

Rationale: Novice Java programmers often use code like: 
    
    
    if (x == "something")
            

when they mean
    
    
    if ("something".equals(x))
            

## Examples

To configure the check: 
    
    
    <module name="StringLiteralEquality"/>

## Further Reading

* [checkstyle - StringLiteralEquality](http://checkstyle.sourceforge.net/config_coding.html#StringLiteralEquality)