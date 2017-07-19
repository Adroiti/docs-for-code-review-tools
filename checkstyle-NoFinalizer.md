Pattern: Use of `finalize()` method

Issue: -

## Description

Finalizers are unpredictable, often dangerous, and generally unnecessary. Their use can cause erratic behavior, poor performance, and portability problems. Finalizers have a few valid uses, but as a rule of thumb, you should avoid them.

## Examples

To configure the check: 


```xml
<module name="NoFinalizer"/>
```

## Further Reading

* [Effective Java, 2nd Edition - Item 7: Avoid finalizers](http://www.informit.com/articles/article.aspx?p=1216151&seqNum=7)
* [Google Java Style Guide - Finalizers: not used](https://google.github.io/styleguide/javaguide.html#s6.4-finalizers)
* [checkstyle - NoFinalizer](http://checkstyle.sourceforge.net/config_coding.html#NoFinalizer)
