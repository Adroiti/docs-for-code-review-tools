Pattern: Use of underscore import

Issue: -

## Description

Importing all classes from a package or static members from a class leads to tight coupling between packages or classes and might lead to problems when a new version of a library introduces name clashes.

## Example configuration
```xml
<pre><check enabled="true" class="org.scalastyle.scalariform.UnderscoreImportChecker" level="warning">
 <parameters>
  <parameter name="ignoreRegex">collection\.JavaConverters\._|scala\.concurrent\.duration\._</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_UppercaseLChecker" />

## Further Reading

* [Databricks Scala Guide - Imports](https://github.com/databricks/scala-style-guide#imports)
* [Scalastyle - UnderscoreImport](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_UnderscoreImportChecker)
