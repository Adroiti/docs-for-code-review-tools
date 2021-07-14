Pattern: Invalid field name

Issue: -

## Description

A consistent naming convention for field names can make code easier to read and understand.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z0-9]*$</td>
      </tr><tr><td>objectFieldRegex</td>
        <td>Regular expression for constants</td>
        <td>string</td>
        <td>^[A-Z][A-Za-z0-9]*$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.FieldNamesChecker" level="warning">
 <parameters>
  <parameter name="regex">^[a-z][A-Za-z0-9]*$</parameter>
  <parameter name="objectFieldRegex">^[A-Z][A-Za-z0-9]*$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_ForBraceChecker" />

## Further Reading

* [Scalastyle - FieldNames](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_FieldNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#constants-values-variable-and-methods)