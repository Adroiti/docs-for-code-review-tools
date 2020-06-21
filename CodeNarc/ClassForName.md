Pattern: Use of `Class.forName()`

Issue: -

## Description

Using `Class.forName(...)` is a common way to add dynamic behavior to a system. However, using this method can cause resource leaks because the classes can be pinned in memory for long periods of time. If you're forced to do dynamic class loading then use `ClassLoader.loadClass` instead. All variations of the `Class.forName(...)` method suffer from the same problem.

Example of violations:

``` groovy
Class.forName('SomeClassName')
Class.forName(aClassName, true, aClassLoader)
```

## Further Reading

* [The Programming Delusion - Class.forName caches defined class in the initiating class loader](http://blog.hargrave.io/2007/09/classforname-caches-defined-class-in.html)
* [CodeNarc - ClassForName](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#classforname-rule)