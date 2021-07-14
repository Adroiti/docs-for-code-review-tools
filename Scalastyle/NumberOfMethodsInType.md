Pattern: Too many methods in type

Issue: -

## Description

If a type declares too many methods, this can be an indication of bad design.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxMethods</td>
        <td>Maximum methods</td>
        <td>integer</td>
        <td>30</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NumberOfMethodsInTypeChecker" level="warning">
 <parameters>
  <parameter name="maxMethods">30</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_NumberOfTypesChecker" />

## Further Reading

* [Scalastyle - NumberOfMethodsInType](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_NumberOfMethodsInTypeChecker)