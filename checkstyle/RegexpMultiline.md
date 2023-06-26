Pattern: Possible issue spanning multiple lines

Issue: -

## Description

A check for detecting that matches across multiple lines. Works with any file type. 

Rationale: This check can be used to when the regular expression can be span multiple lines. 

## Examples

To configure the check to find calls to print to the console: 


```xml
<module name="RegexpMultiline">
  <property name="format"
   value="System\.(out)|(err)\.print(ln)?\("/>
</module>
```

## Further Reading

* [checkstyle - RegexpMultiline](https://checkstyle.sourceforge.io/checks/regexp/regexpmultiline.html#RegexpMultiline)
