Pattern: Method is too long

Issue: -

## Description

Checks for long methods and constructors. 

Rationale: If a method becomes very long it is hard to understand. Therefore long methods should usually be refactored into several individual methods that focus on a specific task. 

## Examples

To configure the check: 
    
    
    <module name="MethodLength"/>
            

To configure the check so that it accepts methods with at most 60 lines: 
    
    
    <module name="MethodLength">
       <property name="tokens" value="METHOD_DEF"/>
       <property name="max" value="60"/>
    </module>
            

To configure the check so that it accepts methods with at most 60 lines, not counting empty lines and single line comments: 
    
    
    <module name="MethodLength">
       <property name="tokens" value="METHOD_DEF"/>
       <property name="max" value="60"/>
       <property name="countEmpty" value="false"/>
    </module>

## Further Reading

* [checkstyle - MethodLength](http://checkstyle.sourceforge.net/config_sizes.html#MethodLength)