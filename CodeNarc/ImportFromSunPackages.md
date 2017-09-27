Pattern: Import from _Sun_ package

Issue: -

This rule rejects all `sun.*` packages since they are internal APIs: they are subject to change in a **undocumented** or **unsupported** way and they are bound to a specific JRE/JDK (Sun in this case), limiting portability of your programs.

Try to avoid uses of such APIs, always prefer a public documented and specified class.

## Description

Example of violations:

``` groovy
import sun.misc.foo
import sun.misc.foo as Foo

public class SomeClass{}
```

## Further Reading

* [CodeNarc - ImportFromSunPackages](http://codenarc.sourceforge.net/codenarc-rules-imports.html#ImportFromSunPackages)