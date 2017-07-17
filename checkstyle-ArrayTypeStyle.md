Pattern: Enforce style of array type definitions

Issue: -

## Description

Checks the style of array type definitions. Some like Java style: `public static void main(String[] args)` and some like C style: `public static void main(String args[])`.

## Examples

To configure the check to enforce Java style: 
    
    
    <module name="ArrayTypeStyle"/>
            

To configure the check to enforce C style: 
    
    
    <module name="ArrayTypeStyle">
        <property name="javaStyle" value="false"/>
    </module>

## Further Reading

* [checkstyle - ArrayTypeStyle](http://checkstyle.sourceforge.net/config_misc.html#ArrayTypeStyle)