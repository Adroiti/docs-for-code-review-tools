Pattern: Multiple statements in one line

Issue: -

## Description

Checks that there is only one statement per line. 

Rationale: It's very difficult to read multiple statements in one line. 

In the Java programming language, statement is a fundamental unit of execution. All statements except blocks are terminated by a semicolon. Blocks are denoted by open and close curly braces. 

The following types of statement are checked: variable declaration statements, empty statements, import statements, assignment statements, expression statements, increment statements, object creation statements, `for loop` statements, `break` statements, `continue` statements, `return` statements. 

## Examples

The following examples will be flagged as a violation: 


```java
//Each line causes violation:
int var1; int var2;
var1 = 1; var2 = 2;
int var1 = 1; int var2 = 2;
var1++; var2++;
Object obj1 = new Object(); Object obj2 = new Object();
import java.io.EOFException; import java.io.BufferedReader;
;; //two empty statements on the same line.
```

```java
//Multi-line statements:
int var1 = 1
; var2 = 2; //violation here
int o = 1, p = 2,
r = 5; int t; //violation here
```
 

An example of how to configure this check: 


```xml
<module name="OneStatementPerLine"/>
```

## Further Reading

* [checkstyle - OneStatementPerLine](http://checkstyle.sourceforge.net/config_coding.html#OneStatementPerLine)
