Pattern: Use of restricted package import

Issue: -

## Description

Controls what can be imported in each package. Useful for ensuring that application layering rules are not violated, especially on large projects. 

Short description of the behaviour: 

  - check starts checking from the longest matching subpackage (later 'current subpackage') described inside import control file to package defined in class file.
  - If there is matching allow/disallow rule inside the current subpackage then the check returns "allowed" or "disallowed" message.
  - If there is no matching allow/disallow rule inside the current subpackage then it continues checking in the parent subpackage.
  - If there is no matching allow/disallow rule in any of the subpackages, including the root level (import-control), then the import is disallowed by default.

The DTD for a import control XML document is at [http://checkstyle.sourceforge.net/dtds/import_control_1_3.dtd](http://checkstyle.sourceforge.net/dtds/import_control_1_3.dtd). It contains documentation on each of the elements and attributes. 

The check validates a XML document when it loads the document. To validate against the above DTD, include the following document type declaration in your XML document: 


```xml
<!DOCTYPE import-control PUBLIC
    "-//Puppy Crawl//DTD Import Control 1.3//EN"
    "http://checkstyle.sourceforge.net/dtds/import_control_1_3.dtd">
```
        

## Examples

To configure the check using an import control file called "config/import-control.xml", then have the following: 


```xml
<module name="ImportControl">
    <property name="file" value="config/import-control.xml"/>
</module>
```
        

To configure the check to only check the "src/main" directory using an import control file called "config/import-control.xml", then have the following: 


```xml
<module name="ImportControl">
    <property name="file" value="config/import-control.xml"/>
    <property name="path" value="^.*[\\/]src[\\/]main[\\/].*$"/>
</module>
```
        

In the example below access to package `com.puppycrawl.tools.checkstyle.checks` and its subpackages is allowed from anywhere in `com.puppycrawl.tools.checkstyle` except from the `filters` subpackage where access to all `check`'s subpackages is disallowed. Two `java.lang.ref` classes are allowed by virtue of one regular expression instead of listing them in two separate allow rules (as it is done with the `Files` and `ClassPath` classes). 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle">
    <disallow pkg="sun"/>
    <allow pkg="com.puppycrawl.tools.checkstyle.api"/>
    <allow pkg="com.puppycrawl.tools.checkstyle.checks"/>
    <allow class="com.google.common.io.Files"/>
    <allow class="com.google.common.reflect.ClassPath"/>
    <subpackage name="filters">
        <allow class="java\.lang\.ref\.(Weak|Soft)Reference"
   regex="true"/>
        <disallow pkg="com\.puppycrawl\.tools\.checkstyle\.checks\.[^.]+"
   regex="true"/>
        <disallow pkg="com.puppycrawl.tools.checkstyle.ant"/>
        <disallow pkg="com.puppycrawl.tools.checkstyle.doclets"/>
        <disallow pkg="com.puppycrawl.tools.checkstyle.gui"/>
    </subpackage>
    <subpackage name="dao">
        <disallow pkg="javax.swing" exact-match="true"/>
    </subpackage>
</import-control>
```
        

In the next example regular expressions are used to enforce a layering rule: In all `dao` packages it is not allowed to access UI layer code (`ui`, `awt`, and `swing`). On the other hand it is not allowed to directly access `dao` and `service` layer from `ui` packages. The root package is also a regular expression that is used to handle old and new domain name with the same rules. 


```xml
<import-control pkg="(de.olddomain|de.newdomain)\..*" regex="true">
    <subpackage pkg="[^.]+\.dao" regex="true">
        <disallow pkg=".*\.ui" regex="true"/>
        <disallow pkg=".*\.(awt|swing).\.*" regex="true"/>
    </subpackage>
    <subpackage pkg="[^.]+\.ui" regex="true">
        <disallow pkg=".*\.(dao|service)" regex="true"/>
    </subpackage>
</import-control>
```
        

In the next examples usage of `strategyOnMismatch` property is shown. This property defines strategy in a case when no matching allow/disallow rule was found. Property `strategyOnMismatch` is attribute of `import-control` and `subpackage` tags. Property can have following values for `import-control` tag: 

  - disallowed (default value) - if there is no matching allow/disallow rule in any of the subpackages, including the root level (import-control), then the import is disallowed.
  - allowed - if there is no matching allow/disallow rule in any of the subpackages, including the root level, then the import is allowed.
And following values for `subpackage` tags: 

  - delegateToParent (default value) - if there is no matching allow/disallow rule inside the current subpackage, then it continues checking in the parent subpackage.
  - allowed - if there is no matching allow/disallow rule inside the current subpackage, then the import is allowed.
  - disallowed - if there is no matching allow/disallow rule inside the current subpackage, then the import is disallowed.

The following example demonstrates usage of `strategyOnMismatch` property for `import-control` tag. Here all imports are allowed except `java.awt.Image` and `java.io.File` classes. 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle.checks" strategyOnMismatch="allowed">
    <disallow class="java.awt.Image"/>
    <disallow class="java.io.File"/>
</import-control>
```
        

In the example below, any import is disallowed inside `com.puppycrawl.tools.checkstyle.checks.imports` package except imports from package `javax.swing` and class `java.io.File`. However, any import is allowed in the classes outside of `com.puppycrawl.tools.checkstyle.checks.imports` package. 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle.checks" strategyOnMismatch="allowed">
    <subpackage name="imports" strategyOnMismatch="disallowed">
        <allow pkg="javax.swing"/>
        <allow class="java.io.File"/>
    </subpackage>
</import-control>
```
        

When `strategyOnMismatch` has `allowed` or `disallowed` value for `subpackage` tag, it makes `subpackage` isolated from parent rules. In the next example, if no matching rule was found inside `com.puppycrawl.tools.checkstyle.checks.filters` then it continues checking in the parent subpackage, while for `com.puppycrawl.tools.checkstyle.checks.imports` import will be allowed by default. 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle.checks">
    <allow class="java\.awt\.Image" regex="true"/>
    <allow class="java\..*\.File" local-only="true" regex="true"/>
    <subpackage name="imports" strategyOnMismatch="allowed">
        <allow pkg="javax\.swing" regex="true"/>
        <allow pkg="java\.io" exact-match="true" local-only="true" regex="true"/>
    </subpackage>
    <subpackage name="filters">
        <allow class="javax.util.Date"/>
    </subpackage>
</import-control>
```
        

For a real-life import control file look at the file called [import-control.xml](https://github.com/checkstyle/checkstyle/blob/master/config/import-control.xml) which is part of the Checkstyle distribution. 

### Example of blacklist mode

To have a **blacklist mode**, it is required to have disallows inside subpackage and to have allow rule inside parent of the current subpackage to catch classes and packages those are not in the blacklist.

In the example below any import from `java.util` (`java.util.List`, `java.util.Date`) package is allowed except `java.util.Map` inside subpackage `com.puppycrawl.tools.checkstyle.filters`.


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle">
    <allow pkg="java.util"/>
    <subpackage name="filters" >
        <disallow class="java.util.Map"/>
    </subpackage>
</import-control>
```
        

In the next example imports `java.util.stream.Stream` and `java.util.stream.Collectors` are disallowed inside `com.puppycrawl.tools.checkstyle.checks.imports` package, but because of `<allow pkg="java.util.stream"/>` every import from `java.util.stream` is allowed except described ones. 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle.checks">
    <allow pkg="java.util.stream"/>
    <subpackage name="imports">
        <disallow class="java.util.stream.Stream"/>
        <disallow class="java.util.stream.Collectors"/>
    </subpackage>
</import-control>
```
        


```java
package com.puppycrawl.tools.checkstyle.checks.imports;
 

import java.util.stream.Stream;     // violation here
import java.util.stream.Collectors; // violation here
import java.util.stream.IntStream;
```
        

In the following example, all imports are allowed except the classes `java.util.Date`, `java.util.List` and package `sun`. 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle.checks">
    <allow pkg=".*" regexp="true"/>
    <subpackage name="imports">
        <disallow class="java.util.Date"/>
        <disallow class="java.util.List"/>
        <disallow pkg="sun"/>
    </subpackage>
</import-control>
```
        

### Notes on regular expressions

Regular expressions in import rules have to match either Java packages or classes. The language rules for packages and class names can be described by the following complicated regular expression that takes into account that Java names may contain any Unicode letter, numbers, underscores, and dollar signs (see section 3.8 in the [Java specs](http://docs.oracle.com/javase/specs/)): 

  - `[\p{Letter}_$][\p{Letter}\p{Number}_$]*` or short `[\p{L}_$][\p{L}\p{N}_$]*` for a class name or package component. 
  - `([\p{L}_$][\p{L}\p{N}_$]*\\.)*[\p{L}_$][\p{L}\p{N}_$]*` for a fully qualified name. 

But it is not necessary to use these complicated expressions since no validation is required. Differentiating between package separator '.' and others is sufficient. Unfortunately '.' has a special meaning in regular expressions so one has to write `\\.` to match an actual dot. 

  - Use `[^.]+` (one or more "not a dot" characters) for a class name or package component. 
  - Use `com\\.google\\.common\\.[^.]+` to match any subpackage of `com.google.common`. 
  - When matching concrete packages like `com.google.common` omitting the backslash before the dots may improve readability and may be just exact enough: `com.google.common\\.[^.]+` matches not only subpackages of `com.google.common` but e.g. also of `com.googleecommon` but you may not care for that. 
  - Do not use `.*` unless you really do not care for what is matched. Often you want to match only a certain package level instead. 

### Notes on inner classes

Static inner classes have to be explicitly allowed when they are imported, they are not automatically allowed along with their enclosing class. 

For example, to allow importing both `java.util.Map` and `java.util.Map.Entry` use the following configuration: 


```xml
<import-control pkg="com.puppycrawl.tools.checkstyle">
    <allow class="java.util.Map"/>
    <allow class="java.util.Map.Entry"/>
</import-control>
```

## Further Reading

* [checkstyle - ImportControl](https://checkstyle.sourceforge.io/checks/imports/importcontrol.html#ImportControl)
