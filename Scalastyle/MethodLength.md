Pattern: Method has too many lines

Issue: -

## Description

Long methods can be hard to read and understand.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxLength</td>
        <td>Maximum length</td>
        <td>integer</td>
        <td>50</td>
      </tr><tr><td>ignoreComments</td>
        <td>Ignore comments</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.MethodLengthChecker" level="warning">
 <parameters>
  <parameter name="maxLength">50</parameter>
  <parameter name="ignoreComments">false</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_MethodNamesChecker" />

## Further Reading

* [Scalastyle - MethodLength](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_MethodLengthChecker)