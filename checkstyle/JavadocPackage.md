Pattern: Incorrect package documentation

Issue: -

## Description

Checks that each Java package has a Javadoc file used for commenting. By default it only allows a `package-info.java` file, but can be configured to allow a `package.html` file. 

An error will be reported if both files exist as this is not allowed by the Javadoc tool. 

## Examples

To configure the check: 


```xml
<module name="JavadocPackage"/>
```

## Further Reading

* [checkstyle - JavadocPackage](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocPackage)
