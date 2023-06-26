Pattern: Statement is line-wrapped

Issue: -

## Description

Checks that chosen statements are not line-wrapped. By default this check restricts wrapping `import` and `package` statements, but it's possible to check any statement. 

## Default configuration

```xml
<module name="NoLineWrap"/>
```

## Examples

Example of **incorrect** code:

```java
import com.puppycrawl.tools. //violation
    checkstyle.api.AbstractCheck;

import static java.math. //violation
    BigInteger.ZERO;
```

Example of **correct** code:

```java
import com.puppycrawl.tools.checkstyle.api.AbstractCheck;
import static java.math.BigInteger.ZERO;
```

To configure the check to force no line-wrapping only in `import` statements:

```xml
<module name="NoLineWrap">
    <property name="tokens" value="IMPORT"/>
</module>
```

## Further Reading

* [Google Java Style Guide - Package statement](https://google.github.io/styleguide/javaguide.html#s3.2-package-statement)
* [Google Java Style Guide - Import statements](https://google.github.io/styleguide/javaguide.html#s3.3.2-import-line-wrapping)
* [checkstyle - NoLineWrap](https://checkstyle.sourceforge.io/checks/whitespace/nolinewrap.html#NoLineWrap)
