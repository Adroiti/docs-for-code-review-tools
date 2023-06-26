Pattern: Malformed operator line wrapping 

Issue: -

## Description

Checks the policy on how to wrap lines on operators. 

## Examples

To configure the check: 


```xml
<module name="OperatorWrap"/>
```
        

To configure the check for the assignment operator, `=`, at the end of a line: 


```xml
<module name="OperatorWrap">
    <property name="tokens" value="ASSIGN"/>
    <property name="option" value="eol"/>
</module>
```

## Further Reading

* [checkstyle - OperatorWrap](https://checkstyle.sourceforge.io/checks/whitespace/operatorwrap.html#OperatorWrap)
