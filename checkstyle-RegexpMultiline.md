Pattern: Implementation of a check that looks that matches across multiple lines in any file type

Issue: -

## Description

A check for detecting that matches across multiple lines. Works with any file type. 

Rationale: This check can be used to when the regular expression can be span multiple lines. 

## Examples

To configure the check to find calls to print to the console: 
    
    
    <module name="RegexpMultiline">
      <property name="format"
       value="System\.(out)|(err)\.print(ln)?\("/>
    </module>

## Further Reading

* [checkstyle - RegexpMultiline](http://checkstyle.sourceforge.net/config_regexp.html#RegexpMultiline)