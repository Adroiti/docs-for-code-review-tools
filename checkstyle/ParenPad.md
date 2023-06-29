Pattern: Malformed padding of parentheses

Issue: -

## Description

Checks the policy on the padding of parentheses; i.e. whether a space is required after a left parenthesis and before a right parenthesis, or such spaces are forbidden, with the exception that it does not check for padding of the right parenthesis at an empty for iterator and empty for initializer. 

## Examples

To configure the check: 


```xml
<module name="ParenPad"/>
```
        

To configure the check to require spaces for the parentheses of constructor, method, and super constructor calls: 


```xml
<module name="ParenPad">
    <property name="tokens" value="CTOR_CALL, METHOD_CALL, SUPER_CTOR_CALL"/>
    <property name="option" value="space"/>
</module>
```

## Further Reading

* [checkstyle - ParenPad](https://checkstyle.sourceforge.io/checks/whitespace/parenpad.html#ParenPad)
