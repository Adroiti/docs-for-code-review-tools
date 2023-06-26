Pattern: Unnecessary `;` in enum

Issue: -

## Description

Checks if unnecessary semicolon is in enum definitions. Semicolon is not needed if enum body contains only enum constants. 

## Examples

To configure the check: 
    
    

    <module name="UnnecessarySemicolonInEnumeration"/>

            

Example of violations 
       

    enum One {

        A,B; // violation

    }

    enum Two {

        A,B,; // violation

    }

    enum Three {

        A,B(); // violation

    }

    enum Four {

        A,B{}; // violation

    }

    enum Five {

        A,

        B

        ; // violation

    }

            

Example of good cases 
    
    
    

    enum Normal {

        A,

        B,

        ; // required ";", no violation

        Normal(){}

    }

    enum NoSemicolon {

        A, B // only enum constants, no semicolon required

    }

## Further Reading

* [checkstyle - UnnecessarySemicolonInEnumeration](https://checkstyle.sourceforge.io/checks/coding/unnecessarysemicoloninenumeration.html)