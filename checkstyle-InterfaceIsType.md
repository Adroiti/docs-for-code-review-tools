Pattern: Implements Bloch, Effective Java, Item 17 - Use Interfaces only to define types

Issue: -

## Description

Implements Joshua Bloch, Effective Java, Item 17 - Use Interfaces only to define types. 

According to Bloch, an interface should describe a _type_. It is therefore inappropriate to define an interface that does not contain any methods but only constants. The Standard class [javax.swing.SwingConstants](http://docs.oracle.com/javase/8/docs/api/javax/swing/SwingConstants.html) is an example of a class that would be flagged by this check. 

The check can be configured to also disallow marker interfaces like `java.io.Serializable`, that do not contain methods or constants at all. 

## Examples

To configure the check: 
    
    
    <module name="InterfaceIsType"/>

## Further Reading

* [checkstyle - InterfaceIsType](http://checkstyle.sourceforge.net/config_design.html#InterfaceIsType)