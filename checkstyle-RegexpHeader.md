Pattern: Possible issue in file header

Issue: -

## Description

Checks the header of a source file against a header that contains a [regular expression](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html) for each line of the source header. 

Rationale: In some projects checking against a fixed header is not sufficient, e.g. the header might require a copyright line where the year information is not static. 

For example, consider the following header: 
    
    
    line  1: ^/{71}$
    line  2: ^// checkstyle:$
    line  3: ^// Checks Java source code for adherence to a set of rules\.$
    line  4: ^// Copyright \(C\) \d\d\d\d  Oliver Burn$
    line  5: ^// Last modification by \$Author.*\$$
    line  6: ^/{71}$
    line  7:
    line  8: ^package
    line  9:
    line 10: ^import
    line 11:
    line 12: ^/\*\*
    line 13: ^ \*([^/]|$)
    line 14: ^ \*/
            

Lines 1 and 6 demonstrate a more compact notation for 71 '/' characters. Line 4 enforces that the copyright notice includes a four digit year. Line 5 is an example how to enforce revision control keywords in a file header. Lines 12-14 is a template for javadoc (line 13 is so complicated to remove conflict with and of Javadoc comment). 

Different programming languages have different comment syntax rules, but all of them start a comment with a non-word character. Hence you can often use the non-word character class to abstract away the concrete comment syntax and allow checking the header for different languages with a single header definition. For example, consider the following header specification (note that this is not the full Apache license header): 
    
    
    line 1: ^#!
    line 2: ^<\?xml.*>$
    line 3: ^\W*$
    line 4: ^\W*Copyright 2006 The Apache Software Foundation or its licensors, as applicable\.$
    line 5: ^\W*Licensed under the Apache License, Version 2\.0 \(the "License"\);$
    line 6: ^\W*$
            

Lines 1 and 2 leave room for technical header lines, e.g. the "#!/bin/sh" line in Unix shell scripts, or the XML file header of XML files. Set the multi-line property to "1, 2" so these lines can be ignored for file types where they do no apply. Lines 3 through 6 define the actual header content. Note how lines 2, 4 and 5 use escapes for characters that have special Regexp semantics. 

## Examples

In default configuration the check does not rise any violations. Default values of properties are used. 
    
    
    <module name="RegexpHeader"/>
              

To configure the check to use header file `"config/java.header"` and `10` and `13` multi-lines: 
    
    
    <module name="RegexpHeader">
        <property name="headerFile" value="config/java.header"/>
        <property name="multiLines" value="10, 13"/>
    </module>
            

To configure the check to verify that each file starts with the header 
    
    
    ^// Copyright \(C\) (\d\d\d\d -)? 2004 MyCompany$
    ^// All rights reserved$
            

without the need for an external header file: 
    
    
    <module name="RegexpHeader">
      <property
        name="header"
        value="^// Copyright \(C\) (\d\d\d\d -)? 2004 MyCompany$\n^// All rights reserved$"/>
    </module>
            

_Note_: `ignoreLines` property has been removed from this check to simplify it. To make some line optional use "^.*$" Regexp for this line.

## Further Reading

* [checkstyle - RegexpHeader](http://checkstyle.sourceforge.net/config_header.html#RegexpHeader)