Pattern: Duplicate string literals

Issue: -

## Description

Code duplication makes maintenance more difficult, so it's better to replace multiple occurrences with a constant.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>allowed</td>
        <td>Maximum occurrences allowed</td>
        <td>integer</td>
        <td>1</td>
      </tr><tr><td>ignoreRegex</td>
        <td>Ignore regular expression</td>
        <td>string</td>
        <td>^""$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.MultipleStringLiteralsChecker" level="warning">
 <parameters>
  <parameter name="allowed">1</parameter>
  <parameter name="ignoreRegex">^\&amp;quot;\&amp;quot;$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_NamedArgumentChecker" />

## Further Reading

* [Scalastyle - MultipleStringLiterals](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_MultipleStringLiteralsChecker)