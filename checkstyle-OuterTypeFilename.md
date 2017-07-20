Pattern: File name and outer type name do not match

Issue: -

## Description

Outer type name and the file name should match to avoid any confusion or misunderstanding. For example, the class `Foo` must be in a file named `Foo.java`. 

## Default configuration: 

```xml
<module name="OuterTypeFilename"/>
```

## Further Reading

* [Google Java Style Guide - File name](https://google.github.io/styleguide/javaguide.html#s2.1-file-name)
* [checkstyle - OuterTypeFilename](http://checkstyle.sourceforge.net/config_misc.html#OuterTypeFilename)
