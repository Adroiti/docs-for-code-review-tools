Pattern: Check that overload methods are grouped together

Issue: -

## Description

Checks that overload methods are grouped together. 

## Examples

Example of incorrect grouping overload methods: 
    
    
    public void foo(int i) {}
    public void foo(String s) {}
    public void notFoo() {} // Have to be after foo(int i, String s)
    public void foo(int i, String s) {}
            

An example of how to configure the check is: 
    
    
    <module name="OverloadMethodsDeclarationOrder"/>

## Further Reading

* [checkstyle - OverloadMethodsDeclarationOrder](http://checkstyle.sourceforge.net/config_coding.html#OverloadMethodsDeclarationOrder)