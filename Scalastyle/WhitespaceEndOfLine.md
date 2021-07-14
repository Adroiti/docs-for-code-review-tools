Pattern: Trailing whitespace

Issue: -

## Description

Whitespace at the end of a line can cause problems when diffing between files or between versions.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>ignoreWhitespaceLines</td>
        <td>Ignore lines with just whitespace</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.WhitespaceEndOfLineChecker" level="warning">
 <parameters>
  <parameter default="false" type="boolean" name="ignoreWhitespaceLines"/>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_BlockImportChecker" />

## Further Reading

* [Scalastyle - WhitespaceEndOfLine](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_WhitespaceEndOfLineChecker)