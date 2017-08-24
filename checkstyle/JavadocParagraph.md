Pattern: Malformed Javadoc paragraph

Issue: -

## Description

Checks that: 

  - There is one blank line between each of two paragraphs and one blank line before the at-clauses block if it is present. 
  - Each paragraph but the first has <p> immediately before the first word, with no space after. 

## Examples

Default configuration: 


```xml
<module name="JavadocParagraph"/>
```
        

To allows to place text of a paragraph not immediately after a <p> tag: 


```xml
<module name="JavadocParagraph">
    <property name="allowNewlineParagraph" value="true"/>
</module>
```
        

In case of tagImmediatelyBeforeFirstWord set to false the following example will not have any violations: 


```java
/**
 * Some Javadoc.
 *
 * <p>
 * Some Javadoc.
 *
 * <p>  Some Javadoc.
 *
 * <p>
 * <pre>
 * Some preformatted Javadoc.
 * </pre>
 *
 */
```

## Further Reading

* [checkstyle - JavadocParagraph](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocParagraph)
