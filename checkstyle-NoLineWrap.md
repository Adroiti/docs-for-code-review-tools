Pattern: Statement is line-wrapped

Issue: -

## Description

Checks that chosen statements are not line-wrapped. By default this check restricts wrapping `import` and `package` statements, but it's possible to check any statement. 

## Examples

Examples of line-wrapped statements (bad case):

```java
package com.puppycrawl. //violation
    tools.checkstyle.checks;

import com.puppycrawl.tools. //violation
    checkstyle.api.AbstractCheck;

import static java.math. //violation
    BigInteger.ZERO;
```


To configure the check to force no line-wrapping in `package` and `import` statements (default values): 

```xml
<module name="NoLineWrap"/>
```


To configure the check to force no line-wrapping only in `import` statements:

```xml
<module name="NoLineWrap">
    <property name="tokens" value="IMPORT"/>
</module>
```


Examples of not line-wrapped statements (good case): 

```java
import com.puppycrawl.tools.checkstyle.api.AbstractCheck;
import static java.math.BigInteger.ZERO;
```


## Further Reading

* [checkstyle - NoLineWrap](http://checkstyle.sourceforge.net/config_whitespace.html#NoLineWrap)
