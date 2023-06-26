Pattern: Invalid custom check

Issue: -

## Description

It is possible to specify an ID of checks, so that it can be leveraged by the SuppressWarningsFilter to skip validations. The following examples show how to skip validations near code that has `@SuppressWarnings("checkstyle:<ID>"`) or just `@SuppressWarnings("<ID>")` annotation, where ID is the ID of checks you want to suppress. 

## Examples

Example of Checkstyle check configuration: 


```xml
<module name="RegexpSinglelineJava">
  <property name="id" value="systemout"/>
  <property name="format" value="^.*System\.(out|err).*$"/>
  <property name="message"
    value="Don't use System.out/err, use SLF4J instead."/>
</module>
```

## Further Reading

* [checkstyle - Filters](https://checkstyle.sourceforge.io/checks/filters/systemout.html#SuppressWarningsFilter)
