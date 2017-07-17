Pattern: Illegal throwable object

Issue: -

## Description

This check can be used to ensure that types are not declared to be thrown. Declaring that a method throws `java.lang.Error` or `java.lang.RuntimeException` is almost never acceptable. 

## Examples

To configure the check: 
    
    
    <module name="IllegalThrows"/>
            

To configure the check rejecting throws `NullPointerException` from methods: 
    
    
    <module name="IllegalThrows">
        <property name="illegalClassNames" value="NullPointerException"/>
    </module>
            

To configure the check ignoring method named "foo()": 
    
    
    <module name="IllegalThrows">
        <property name="ignoredMethodNames" value="foo"/>
    </module>
            

To configure the check to warn on overridden methods: 
    
    
    <module name="IllegalThrows">
        <property name="ignoreOverriddenMethods" value="false"/>
    </module>

## Further Reading

* [checkstyle - IllegalThrows](http://checkstyle.sourceforge.net/config_coding.html#IllegalThrows)