Pattern: Missing braces around code block

Issue: -

## Description

Checks for braces around code blocks. 

## Examples

To configure the check: 


```xml
<module name="NeedBraces"/>
```
        

To configure the check for `if` and `else` blocks: 


```xml
<module name="NeedBraces">
    <property name="tokens" value="LITERAL_IF, LITERAL_ELSE"/>
</module>
```
        

To configure the check to allow single-line statements (`if, while, do-while, for`) without braces: 


```xml
<module name="NeedBraces">
    <property name="allowSingleLineStatement" value="true"/>
</module>
```
        

Next statements won't be violated by Check: 


```java
if (obj.isValid()) return true; // OK
while (obj.isValid()) return true; // OK
do this.notify(); while (o != null); // OK
for (int i = 0; ; ) this.notify(); // OK
```
        

To configure the check to allow `case, default` single-line statements without braces: 


```xml
<module name="NeedBraces">
    <property name="tokens" value="LITERAL_CASE, LITERAL_DEFAULT"/>
    <property name="allowSingleLineStatement" value="true"/>
</module>
```
        

Next statements won't be violated by Check: 


```java
switch (num) {
    case 1: counter++; break; // OK
    case 6: counter += 10; break; // OK
    default: counter = 100; break; // OK
}
```
        

To configure the check to allow loops (`while, for`) with empty bodies: 


```xml
<module name="NeedBraces">
    <property name="allowEmptyLoopBody" value="true"/>
</module>
```
 

Next statements won't be violated by Check: 


```java
while (value.incrementValue() < 5); // OK
for(int i = 0; i < 10; value.incrementValue()); // OK
```

## Further Reading

* [checkstyle - NeedBraces](http://checkstyle.sourceforge.net/config_blocks.html#NeedBraces)
