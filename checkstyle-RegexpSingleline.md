Pattern: Implementation of a check that looks for a single line in any file type

Issue: -

## Description

A check for detecting single lines that match a supplied regular expression. Works with any file type. 

Rationale: This check can be used to prototype checks and to find common bad practice such as calling `ex.printStacktrace()`, ` System.out.println()`, `System.exit()`, etc. 

## Examples

To configure the check to find trailing whitespace at the end of a line: 
    
    
    <module name="RegexpSingleline">
      <!-- \s matches whitespace character, $ matches end of line. -->
      <property name="format" value="\s+$"/>
    </module>
            

To configure the check to find trailing whitespace at the end of a line, with some _slack_ of allowing two occurrences per file: 
    
    
    <module name="RegexpSingleline">
      <property name="format" value="\s+$"/>
      <!-- next line not required as 0 is the default -->
      <property name="minimum" value="0"/>
      <property name="maximum" value="2"/>
    </module>
            

An example of how to configure the check to make sure a copyright statement is included in the file: 
    
    
    <module name="RegexpSingleline">
      <property name="format" value="This file is copyrighted"/>
      <property name="minimum" value="1"/>
      <!--  Need to specify a maximum, so 10 times is more than enough. -->
      <property name="maximum" value="10"/>
    </module>

## Further Reading

* [checkstyle - RegexpSingleline](http://checkstyle.sourceforge.net/config_regexp.html#RegexpSingleline)