Pattern: Malformed class package declaration

Issue: -

## Description

Ensures that a class has a package declaration, and (optionally) whether the package name matches the directory name for the source file. 

Rationale: Classes that live in the null package cannot be imported. Many novice developers are not aware of this. 

Packages provide logical namespace to classes and should be stored in the form of directory levels to provide physical grouping to your classes. These directories are added to the classpath so that your classes are visible to JVM when it runs the code. 

## Examples

To configure the check: 


```xml
<module name="PackageDeclaration"/>
```
        

Let us consider the class AnnotationLocationCheck which is in the directory /com/puppycrawl/tools/checkstyle/checks/annotations/ 


```java
package com.puppycrawl.tools.checkstyle.checks; //Violation
public class AnnotationLocationCheck extends AbstractCheck {
//...
}
```
        

Example of how the check works when matchDirectoryStructure option is set to false. Let us again consider the AnnotationLocationCheck class located at directory /com/puppycrawl/tools/checkstyle/checks/annotations/ along with the following setup, 


```xml
<module name="PackageDeclaration">
<property name="matchDirectoryStructure" value="false"/>
</module>
```
        


```java
package com.puppycrawl.tools.checkstyle.checks;  //No Violation
```

```java
public class AnnotationLocationCheck extends AbstractCheck {
//...
}
```

## Further Reading

* [checkstyle - PackageDeclaration](http://checkstyle.sourceforge.net/config_coding.html#PackageDeclaration)
