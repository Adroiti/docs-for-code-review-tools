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
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.file.WhitespaceEndOfLineChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter default=&quot;false&quot; type=&quot;boolean&quot; name=&quot;ignoreWhitespaceLines&quot;/&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_BlockImportChecker" />

## Further Reading

* [Scalastyle - WhitespaceEndOfLine](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_file_WhitespaceEndOfLineChecker)