Pattern: Regex-based issue

Issue: -

## Description

This rule reports issues captured with a regular expression.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td></td>
      </tr><tr><td>line</td>
        <td>Line</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.RegexChecker" level="warning">
 <parameters>
  <parameter name="regex">(?m)^\s*$(\r|)\n^\s*$(\r|)\n</parameter>
  <parameter name="line">false</parameter>
 </parameters>
 <customMessage>No double blank lines</customMessage>
</check>
```
<a name="org_scalastyle_file_WhitespaceEndOfLineChecker" />

## Further Reading

* [Scalastyle - Regex](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_RegexChecker)