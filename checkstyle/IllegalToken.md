Pattern: Illegal token

Issue: -

## Description

Checks for illegal tokens. By default labels are prohibited. 

Rationale: Certain language features can harm readability, lead to confusion or are not obvious to novice developers. Other features may be discouraged in certain frameworks, such as not having native methods in Enterprise JavaBeans components. 

## Examples

To configure the check to find token LITERAL_NATIVE: 


```xml
<module name="IllegalToken">
    <property name="tokens" value="LITERAL_NATIVE"/>
</module>
```

## Further Reading

* [checkstyle - IllegalToken](https://checkstyle.sourceforge.io/checks/coding/illegaltoken.html#IllegalToken)
