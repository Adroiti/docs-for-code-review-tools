Pattern: Malformed file header

Issue: -

## Description

A lot of projects require a header with a copyright notice, or they require a license in each file. This does a simple text comparison between the header and the first lines of the file. You can have multiple lines, but make sure you surround the text with a `CDATA` section. You can also specify a regular expression, as long as you set the regex parameter to true.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>header</td>
        <td>Header</td>
        <td>string</td>
        <td></td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.HeaderMatchesChecker" level="warning">
 <parameters>
  <parameter name="regex">false</parameter>
  <parameter name="header">// Copyright \(C\) 2011-2012 the original author or authors.</parameter>
 </parameters>
</check>
```
or

```xml
<check enabled="true" class="org.scalastyle.file.HeaderMatchesChecker" level="warning">
 <parameters>
  <parameter name="regex">true</parameter>
  <parameter name="header">// Copyright \(C\) (?:\d{4}-)?\d{4} the original author or authors.</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_file_IndentationChecker" />

## Further Reading

* [Scalastyle - HeaderMatches](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_HeaderMatchesChecker)