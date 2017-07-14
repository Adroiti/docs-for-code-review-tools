Pattern: Check that each variable declaration is in its own statement and on its own line

Issue: -

## Description

Checks that each variable declaration is in its own statement and on its own line. 

Rationale: [ the Java code conventions chapter 6.1](http://www.oracle.com/technetwork/java/javase/documentation/codeconventions-141270.html#2992) recommends that declarations should be one per line/statement. 

## Examples

To configure the check: 
    
    
    <module name="MultipleVariableDeclarations"/>

## Further Reading

* [checkstyle - MultipleVariableDeclarations](http://checkstyle.sourceforge.net/config_coding.html#MultipleVariableDeclarations)