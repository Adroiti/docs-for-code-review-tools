Pattern: Unnecessary `;` in last resource declaration

Issue: -

## Description

Checks if unnecessary semicolon is used in last resource declaration. 

## Examples

To configure the check: 
    

    <module name="UnnecessarySemicolonInTryWithResources"/>

            

Example of violations 
    

    class A {

        void method() throws IOException {

            try(Reader r1 = new PipedReader();){} // violation

            try(Reader r4 = new PipedReader();Reader r5 = new PipedReader()

            ;){} // violation

            try(Reader r6 = new PipedReader();

                Reader r7

                       = new PipedReader();

            ){}

        }

    }

            

To configure the check to detect unnecessary semicolon if closing paren is not on same line 
    

    <module name="UnnecessarySemicolonInTryWithResources">

      <property name="allowWhenNoBraceAfterSemicolon" value="false"/>

    </module>

            

Example of exclusion 
    
    

    class A {

        void method() throws IOException {

            try(Reader r1 = new PipedReader();){} // violation

            try(Reader r6 = new PipedReader();

                Reader r7 = new PipedReader(); // violation

            ){}

        }

    }

## Further Reading

* [checkstyle - UnnecessarySemicolonInTryWithResources](https://checkstyle.sourceforge.io/checks/coding/unnecessarysemicolonintrywithresources.html)