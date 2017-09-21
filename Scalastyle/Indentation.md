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
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.file.IndentationChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;tabSize&quot;&gt;2&lt;/parameter&gt;
  &lt;parameter name=&quot;methodParamIndentSize&quot;&gt;2&lt;/parameter&gt;
  &lt;parameter name=&quot;classParamIndentSize&quot;&gt;4&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_file_NewLineAtEofChecker" />

## Further Reading

* [Scalastyle - Indentation](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_file_IndentationChecker)