Pattern: Forbidden phrase in Javadoc summary

Issue: -

## Description

Checks that [Javadoc summary sentence](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html#firstsentence) does not contain phrases that are not recommended to use. Summaries that contain only the `{@inheritDoc}` tag are skipped. 

## Examples

By default check validate that first sentence is not empty: 


```xml
<module name="SummaryJavadocCheck"/>
```
        

Example of `{@inheritDoc}` without summary. 


```java
```
 
```java
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
```
        
```java
```
        

To ensure that summary do not contain phrase like "This method returns" , use following config: 


```xml
<module name="SummaryJavadocCheck">
    <property name="forbiddenSummaryFragments" value="^This method returns.*"/>
</module>
```
        

To specify period symbol at the end of first Javadoc sentence: 


```xml
<module name="SummaryJavadocCheck">
    <property name="period" value="。"/>
</module>
```
        

Example of period property. 


```java
public class TestClass {
   /**
    * This is invalid Javadoc
    */
    void invalidJavadocMethod() {
    }
   /**
    * This is valid Javadoc
    */
    void validJavadocMethod() {
    }
}
```

## Further Reading

* [checkstyle - SummaryJavadoc](https://checkstyle.sourceforge.io/checks/javadoc/summaryjavadoc.html#SummaryJavadoc)
