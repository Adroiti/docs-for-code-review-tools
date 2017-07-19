Pattern: Class relies on too many other classes

Issue: -

## Description

In other other words, class fan-out complexity is too high. It has direct impact on amount of maintenance required in functional programs. This check processes files in the following way:

  1. Iterates over the list of tokens (defined below) and counts all mentioned classes. 
```java
- [PACKAGE_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#PACKAGE_DEF)
- [IMPORT](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#IMPORT)
- [CLASS_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#CLASS_DEF)
- [INTERFACE_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#INTERFACE_DEF)
- [ENUM_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#ENUM_DEF)
- [TYPE](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#TYPE)
- [LITERAL_NEW](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#LITERAL_NEW)
- [LITERAL_THROWS ](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#LITERAL_THROWS)
- [ANNOTATION_DEF ](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#ANNOTATION_DEF)
  2. If a class was imported with direct import (i.e. `import java.math.BigDecimal`), or the class was referenced with the package name (i.e. `java.math.BigDecimal value`) and the package was added to the `excludedPackages` parameter, the class does not increase complexity. 
  3. If a class name was added to the `excludedClasses` parameter, the class does not increase complexity. 
```

## Examples

To configure the check: 


```xml
<module name="ClassFanOutComplexity"/>
```
        

To configure the check with a threshold of 10: 


```xml
<module name="ClassFanOutComplexity">
    <property name="max" value="10"/>
</module>
```
        

Override property `excludedPackages` to mark some packages as excluded. Each member of `excludedPackages` should be a valid identifier: 

  - `java.util` \- valid, excludes all classes inside `java.util`, but not from the subpackages. 
  - `java.util.` \- invalid, should not end with a dot. 
  - `java.util.*` \- invalid, should not end with a star. 

Note, that checkstyle will ignore all classes from the `java.lang` package and its subpackages, even if the `java.lang` was not listed in the `excludedPackages` parameter. 

Also node, that `excludedPackages` will not exclude classes, imported via wildcard (e.g. `import java.math.*`). Instead of wildcard import you should use direct import (e.g. `import java.math.BigDecimal`). 

Also note, that checkstyle will not exclude classes within the same file even if it was listed in the `excludedPackages` parameter. For example, assuming the config is 


```xml
<module name="ClassDataAbstractionCoupling">
    <property name="excludedPackages" value="a.b"/>
</module>
```
 

And the file `a.b.Foo.java` is: 


```java
package a.b;
 

import a.b.Bar;
import a.b.c.Baz;
 

public class Foo {
    public Bar bar; // Will be ignored, located inside ignored a.b package
    public Baz baz; // Will not be ignored, located inside a.b.c package
    public Data data; // Will not be ignored, same file
 

    class Data {
        public Foo foo; // Will not be ignored, same file
    }
}
```
 

The `bar` member will not be counted, since the `a.b` added to the `excludedPackages`. The `baz` member will be counted, since the `a.b.c` was not added to the `excludedPackages`. The `data` and `foo` members will be counted, as they are inside same file. 

Example of usage: 


```xml
<module name="ClassFanOutComplexity">
    <property name="excludedPackages" value="java.util, java.math"/>
</module>
```

## Further Reading

* [checkstyle - ClassFanOutComplexity](http://checkstyle.sourceforge.net/config_metrics.html#ClassFanOutComplexity)
