Pattern: Too many types declared in file

Issue: -

## Description

If there are too many classes/objects defined in a single file, this can cause the code to be difficult to understand.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxTypes</td>
        <td>Maximum Number</td>
        <td>integer</td>
        <td>20</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NumberOfTypesChecker" level="warning">
 <parameters>
  <parameter name="maxTypes">20</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_ObjectNamesChecker" />

## Further Reading

* [Scalastyle - NumberOfTypes](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NumberOfTypesChecker)