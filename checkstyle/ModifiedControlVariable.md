Pattern: Control variable is modified

Issue: -

## Description

Check for ensuring that `for` loop control variables are not modified inside the `for` block. An example is: 


```java
  for (int i = 0; i < 1; i++) {
i++; //violation
  }
```
        

Rationale: If the control variable is modified inside the loop body, the program flow becomes more difficult to follow.  
See [FOR statement](http://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.14) specification for more details. 

Such loop would be suppressed: 


```java
   for (int i = 0; i < 10;) {
   i++;
   }
```
        

## Examples

To configure the check: 


```xml
<module name="ModifiedControlVariable"/>
```
        

By default, This check validates [Enhanced For-Loop](http://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.14.2). 

Option 'skipEnhancedForLoopVariable' could be used to skip check of variable from Enhanced For Loop. 

An example of how to configure the check so that it skips enhanced For Loop Variable is: 


```java
<module name="ModifiedControlVariable">
<property name="skipEnhancedForLoopVariable" value="true"/>
</module>
```


Example:


```java
for ( String line: lines ) {
line = line.trim();   // it will skip this violation
}
```

## Further Reading

* [checkstyle - ModifiedControlVariable](https://checkstyle.sourceforge.io/checks/coding/modifiedcontrolvariable.html#ModifiedControlVariable)
