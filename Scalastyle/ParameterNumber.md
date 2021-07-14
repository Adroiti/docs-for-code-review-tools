Pattern: Too many method parameters

Issue: -

## Description

A method which has more than a certain number of parameters can be hard to understand.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxParameters</td>
        <td>Maximum Number</td>
        <td>integer</td>
        <td>8</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ParameterNumberChecker" level="warning">
 <parameters>
  <parameter name="maxParameters">8</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_PatternMatchAlignChecker" />

## Further Reading

* [Scalastyle - ParameterNumber](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ParameterNumberChecker)