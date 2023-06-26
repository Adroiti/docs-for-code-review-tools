Pattern: Possible single line issue in Java file

Issue: -

## Description

This class is variation on RegexpSingleline for detecting single lines that match a supplied regular expression in Java files. It supports suppressing matches in Java comments. 

## Examples

To configure the check for calls to `System.out.println`, except in comments: 


```xml
<module name="RegexpSinglelineJava">
    <!-- . matches any character, so we need to
escape it and use \. to match dots. -->
  <property name="format" value="System\.out\.println"/>
  <property name="ignoreComments" value="true"/>
</module>
```
        

To configure the check to find case-insensitive occurrences of "debug": 


```xml
<module name="RegexpSinglelineJava">
    <property name="format" value="debug"/>
    <property name="ignoreCase" value="true"/>
</module>
```

## Further Reading

* [checkstyle - RegexpSinglelineJava](https://checkstyle.sourceforge.io/checks/regexp/regexpsinglelinejava.html#RegexpSinglelineJava)
