Pattern: Too many Non Commenting Source Statements (NCSS)

Issue: -

## Description

Determines complexity of methods, classes and files by counting the Non Commenting Source Statements (NCSS). This check adheres to the [specification](http://www.kclee.de/clemens/java/javancss/#specification) for the [JavaNCSS-Tool](http://www.kclee.de/clemens/java/javancss/) written by **Chr. Clemens Lee**.  
Roughly said the NCSS metric is calculated by counting the source lines which are not comments, (nearly) equivalent to counting the semicolons and opening curly braces.  
The NCSS for a class is summarized from the NCSS of all its methods, the NCSS of its nested classes and the number of member variable declarations.  
The NCSS for a file is summarized from the ncss of all its top level classes, the number of imports and the package declaration. 

Rationale: Too large methods and classes are hard to read and costly to maintain. A large NCSS number often means that a method or class has too many responsibilities and/or functionalities which should be decomposed into smaller units. 

## Examples

To configure the check: 


```xml
<module name="JavaNCSS"/>
```
        

To configure the check with 40 allowed non commenting lines for a method: 


```xml
<module name="JavaNCSS">
    <property name="methodMaximum" value="40"/>
</module>
```

## Further Reading

* [checkstyle - JavaNCSS](https://checkstyle.sourceforge.io/checks/metrics/javancss.html#JavaNCSS)
