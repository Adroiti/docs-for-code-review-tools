Pattern: Check that Javadoc summary sentence does not contain phrases that are not recommended to use

Issue: -

## Description

Checks that [ Javadoc summary sentence](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html#firstsentence) does not contain phrases that are not recommended to use. Summaries that contain only the `{@inheritDoc}` tag are skipped. 

## Examples

By default check validate that first sentence is not empty: 
    
    
    <module name="SummaryJavadocCheck"/>
            

Example of `{@inheritDoc}` without summary. 
    
    
              
      public class Test extends Exception {
      //Valid
        /**
         * {@inheritDoc}
         */
        public String ValidFunction(){
          return "";
        }
        //Violation
        /**
         *
         */
        public String InvalidFunction(){
          return "";
        }
      }
            
            

To ensure that summary do not contain phrase like "This method returns" , use following config: 
    
    
    <module name="SummaryJavadocCheck">
        <property name="forbiddenSummaryFragments" value="^This method returns.*"/>
    </module>
            

To specify period symbol at the end of first javadoc sentence: 
    
    
    <module name="SummaryJavadocCheck">
        <property name="period" value="。"/>
    </module>
            

Example of period property. 
    
    
    public class TestClass {
       /**
        * This is invalid java doc.
        */
        void invalidJavaDocMethod() {
        }
       /**
        * This is valid java doc。
        */
        void validJavaDocMethod() {
        }
    }

## Further Reading

* [checkstyle - SummaryJavadoc](http://checkstyle.sourceforge.net/config_javadoc.html#SummaryJavadoc)