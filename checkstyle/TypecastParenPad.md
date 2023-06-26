Pattern: Wrong padding of parentheses for typecast

Issue: -

## Description

Checks the policy on the padding of parentheses for typecasts. That is, whether a space is required after a left parenthesis and before a right parenthesis, or such spaces are forbidden. 

## Examples

To configure the check: 


```xml
<module name="TypecastParenPad"/>
```
        

To configure the check to require spaces: 


```xml
<module name="TypecastParenPad">
    <property name="option" value="space"/>
</module>
```

## Further Reading

* [checkstyle - TypecastParenPad](https://checkstyle.sourceforge.io/checks/whitespace/typecastparenpad.html#TypecastParenPad)
