Pattern: Fall-through in `switch` statement

Issue: -

## Description

Checks for fall-through in `switch` statements. Finds locations where a `case` **contains** Java code but lacks a `break`, `return`, `throw` or `continue` statement.

The check honors special comments to suppress the warning. By default the text "fallthru", "fall through", "fallthrough", "falls through" and "fallsthrough" are recognized (case sensitive). The comment containing these words must be all on one line, and must be on the last non-empty line before the `case` triggering the warning or on the same line before the `case` (ugly, but possible).


```java
switch (i){
case 0:
    i++; // fall through
 

case 1:
    i++;
    // falls through
case 2:
case 3:
case 4: {
    i++;
}
// fallthrough
case 5:
    i++;
/* fallthru */case 6:
    i++
    break;
}
```
        

Note: The check assumes that there is no unreachable code in the `case`. 

## Examples

To configure the check: 


```xml
<module name="FallThrough"/>
```
        

or 


```xml
<module name="FallThrough">
    <property name="reliefPattern" value="continue in next case"/>
</module>
```

## Further Reading

* [checkstyle - FallThrough](http://checkstyle.sourceforge.net/config_coding.html#FallThrough)
