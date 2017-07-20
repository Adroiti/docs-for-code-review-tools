Pattern: File name and outer type name do not match

Issue: -

## Description

To avoid any confusion or misunderstanding, outer type name and the file name shiuld. For example, the class `Foo` must be in a file named `Foo.java`. 

## Examples

To configure the check: 


```xml
<module name="OuterTypeFilename"/>
```

## Further Reading

* [Google Java Style Guide - File name](https://google.github.io/styleguide/javaguide.html#s2.1-file-name)
* [checkstyle - OuterTypeFilename](http://checkstyle.sourceforge.net/config_misc.html#OuterTypeFilename)
