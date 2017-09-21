Pattern: Regex-based result

Issue: -

## Description

Some checks can be carried out with a regular expression.

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
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.file.RegexChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;(?m)^\s*$(\r|)\n^\s*$(\r|)\n&lt;/parameter&gt;
  &lt;parameter name=&quot;line&quot;&gt;false&lt;/parameter&gt;
 &lt;/parameters&gt;
 &lt;customMessage&gt;No double blank lines&lt;/customMessage&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_file_WhitespaceEndOfLineChecker" />

## Further Reading

* [Scalastyle - Regex](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_file_RegexChecker)