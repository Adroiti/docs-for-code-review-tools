Pattern: Invalid object name

Issue: -

## Description

The Scala style guide recommends that object names conform to certain standards.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[A-Z][A-Za-z]*$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ObjectNamesChecker" level="warning">
 <parameters>
  <parameter name="regex">^[A-Z][A-Za-z]*$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_OverrideJavaChecker" />

## Further Reading

* [Scalastyle - ObjectNames](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ObjectNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#objects)