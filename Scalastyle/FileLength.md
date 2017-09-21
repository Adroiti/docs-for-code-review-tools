Pattern: Too many lines in file

Issue: -

## Description

Limiting the number of lines allowed in a file allows files to remain small, single purpose, and maintainable.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxFileLength</td>
        <td>Maximum file length</td>
        <td>integer</td>
        <td>1500</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.file.FileLengthChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;maxFileLength&quot;&gt;800&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_file_FileLineLengthChecker" />

## Further Reading

* [Scalastyle - FileLength](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_file_FileLengthChecker)