Pattern: Inconsistent indentation

Issue: -

## Description

Code that is not indented consistently can be hard to read.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>tabSize</td>
        <td>Tab size</td>
        <td>integer</td>
        <td>2</td>
      </tr><tr><td>methodParamIndentSize</td>
        <td>Multi-line method parameter spacing</td>
        <td>integer</td>
        <td>2</td>
      </tr><tr><td>classParamIndentSize</td>
        <td>Multi-line class parameter spacing</td>
        <td>integer</td>
        <td>4</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.IndentationChecker" level="warning">
 <parameters>
  <parameter name="tabSize">2</parameter>
  <parameter name="methodParamIndentSize">2</parameter>
  <parameter name="classParamIndentSize">4</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_file_NewLineAtEofChecker" />

## Further Reading

* [Scalastyle - Indentation](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_IndentationChecker)