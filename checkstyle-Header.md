Pattern: Malformed file header

Issue: -

## Description

Checks that a source file begins with a specified header. Property `headerFile` specifies a file that contains the required header. Alternatively, the header specification can be set directly in the `header` property without the need for an external file. 

Property `ignoreLines` specifies the line numbers to ignore when matching lines in a header file. This property is very useful for supporting headers that contain copyright dates. For example, consider the following header: 
    
    
    line 1: ////////////////////////////////////////////////////////////////////
    line 2: // checkstyle:
    line 3: // Checks Java source code for adherence to a set of rules.
    line 4: // Copyright (C) 2002  Oliver Burn
    line 5: ////////////////////////////////////////////////////////////////////
            

Since the year information will change over time, you can tell Checkstyle to ignore line 4 by setting property `ignoreLines` to `4`. 

## Examples

In default configuration the check does not rise any violations. Default values of properties are used. 
    
    
    <module name="Header"/>
              

To configure the check to use header file `"config/java.header"` and ignore lines `2`, `3`, and `4` and only process Java files: 
    
    
    <module name="Header">
        <property name="headerFile" value="config/java.header"/>
        <property name="ignoreLines" value="2, 3, 4"/>
        <property name="fileExtensions" value="java"/>
    </module>
            

To configure the check to verify that each file starts with the header 
    
    
    // Copyright (C) 2004 MyCompany
    // All rights reserved
            

without the need for an external header file: 
    
    
    <module name="Header">
        <property name="header"
                  value="// Copyright (C) 2004 MyCompany\n// All rights reserved"/>
    </module>

## Further Reading

* [checkstyle - Header](http://checkstyle.sourceforge.net/config_header.html#Header)