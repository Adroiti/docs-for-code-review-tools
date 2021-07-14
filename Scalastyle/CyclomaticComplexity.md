Pattern: Cyclomatic complexity is too high

Issue: -

## Description

If the code is too complex, then this can make code hard to read.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maximum</td>
        <td>Maximum</td>
        <td>integer</td>
        <td>10</td>
      </tr><tr><td>countCases</td>
        <td>Count Cases</td>
        <td>boolean</td>
        <td>true</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.CyclomaticComplexityChecker" level="warning">
 <parameters>
  <parameter name="maximum">10</parameter>
  <parameter name="countCases">true</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_DeprecatedJavaChecker" />

## Further Reading

* [Scalastyle - CyclomaticComplexity](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_CyclomaticComplexityChecker)