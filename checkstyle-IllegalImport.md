Pattern: Import from illegal package

Issue: -

## Description

By default this rule rejects all `sun.*` packages since they are internal APIs: they are subject to change in a **undocumented** or **unsupported** way and they are bound to a specific JRE/JDK (Sun in this case), limiting portability of your programs.

Try to avoid uses of such APIs, always prefer a public documented and specified class.

## Default configuration

```xml
<module name="IllegalImport"/>
```

## Examples

Example of **incorrect** code:

```java
import sun.misc.Cleaner
```

Example of **correct** code:

```java
import java.lang.ref.Cleaner // standard replacement for sun.misc.Cleaner
```


## Further Reading

* [Oracle Technology Network - Why Developers Should Not Write Programs 
That Call 'sun' Packages](http://www.oracle.com/technetwork/java/faq-sun-packages-142232.html)
* [checkstyle - IllegalImport](http://checkstyle.sourceforge.net/config_imports.html#IllegalImport)
