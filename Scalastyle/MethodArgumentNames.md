Pattern: Invalid method argument name

Issue: -

## Description

The Scala style guide recommends that method argument names conform to certain standards.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z0-9]*$</td>
      </tr><tr><td>ignoreRegex</td>
        <td>Regular expression to ignore</td>
        <td>string</td>
        <td>^$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.MethodArgumentNamesChecker" level="warning">
 <parameters>
  <parameter name="regex">^[a-z][A-Za-z0-9]*$</parameter>
  <parameter name="ignoreRegex">^$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_MethodLengthChecker" />

## Further Reading

* [Scalastyle - MethodArgumentNames](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_MethodArgumentNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#methods)