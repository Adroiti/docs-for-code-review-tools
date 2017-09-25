Pattern: Invalid package name

Issue: -

## Description

The Scala style guide recommends that package names conform to certain standards.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z]*$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.PackageNamesChecker" level="warning">
 <parameters>
  <parameter name="regex">^[a-z][A-Za-z]*$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_PackageObjectNamesChecker" />

## Further Reading

* [Scalastyle - PackageNames](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_PackageNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#packages)