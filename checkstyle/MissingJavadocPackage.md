Pattern: Missing Javadoc comments in `package-info.java`

Issue: -

## Description

Checks for missing Javadoc comments in `package-info.java` files. 

Rationale: description and other related documentation for a package can be written up in the package-info.java file and it gets used in the production of the Javadocs.

## Examples

To configure the check: 
    
    

    <module name="MissingJavadocPackage"/>

            

Example:
    

    /**

    * Provides API classes

    */

    package com.checkstyle.api; // no violation

    /*

    * Block comment is not a javadoc

    */

    package com.checkstyle.api; // violation

## Further Reading

* [checkstyle - MissingJavadocPackage](https://checkstyle.sourceforge.io/checks/javadoc/missingjavadocpackage.html)