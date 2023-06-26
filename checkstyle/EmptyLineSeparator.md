Pattern: Misuse of empty line separator

Issue: -

## Description

Checks for empty line separators after header, package, all import declarations, fields, constructors, methods, nested classes, static initializers and instance initializers. 

ATTENTION: empty line separator is required between AST siblings, not after line where token is found. 

## Examples

Example of declarations without empty line separator: 


```java
///////////////////////////////////////////////////
//HEADER
///////////////////////////////////////////////////
package com.puppycrawl.tools.checkstyle.whitespace;
import java.io.Serializable;
class Foo
{
    public static final int FOO_CONST = 1;
    public void foo() {} //should be separated from previous statement.
}
```
      

An example of how to configure the check with default parameters is: 


```xml
<module name="EmptyLineSeparator"/>
```
      

Example of declarations with empty line separator that is expected by the check by default: 


```java
///////////////////////////////////////////////////
//HEADER
///////////////////////////////////////////////////
 
package com.puppycrawl.tools.checkstyle.whitespace;
 
import java.io.Serializable;
 
class Foo
{
    public static final int FOO_CONST = 1;

    public void foo() {} //should be separated from previous statement.
}
```


An example how to check empty line after [VARIABLE_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#VARIABLE_DEF) and [METHOD_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#METHOD_DEF): 


```xml
<module name="EmptyLineSeparator">
    <property name="tokens" value="VARIABLE_DEF, METHOD_DEF"/>
</module>
```
      

An example how to allow no empty line between fields: 


```xml
<module name="EmptyLineSeparator">
    <property name="allowNoEmptyLineBetweenFields" value="true"/>
</module>
```
      

An example how to disallow multiple empty lines inside constructor, initialization block and method: 


```xml
<module name="EmptyLineSeparator">
    <property name="allowMultipleEmptyLinesInsideClassMembers" value="false"/>
</module>
```
      

The check is valid only for statements that have body: [CLASS_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#CLASS_DEF), [INTERFACE_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#INTERFACE_DEF), [ENUM_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#ENUM_DEF), [STATIC_INIT](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#METHOD_DEF), [INSTANCE_INIT](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#INSTANCE_INIT), [METHOD_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#METHOD_DEF), [CTOR_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#CTOR_DEF), 

Example of declarations with multiple empty lines inside method: 


```java
///////////////////////////////////////////////////
//HEADER
///////////////////////////////////////////////////

package com.puppycrawl.tools.checkstyle.whitespace;

class Foo
{
 
    public void foo() {
 
 
        System.out.println(1); // violation since method has 2 empty lines subsequently
  }
}
```

## Further Reading

* [checkstyle - EmptyLineSeparator](https://checkstyle.sourceforge.io/checks/whitespace/emptylineseparator.html#EmptyLineSeparator)
