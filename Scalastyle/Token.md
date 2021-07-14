Pattern: Illegal token

Issue: -

## Description

This rule reports issues captured with a regular expression token.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.TokenChecker" level="warning">
 <parameters>
  <parameter name="regex">^[ai]sInstanceOf$</parameter>
 </parameters>
 <customMessage>Avoid casting.</customMessage>
</check>
```
<a name="org_scalastyle_scalariform_UnderscoreImportChecker" />

## Further Reading

* [Scalastyle - Token](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_TokenChecker)