Pattern: String literal appears multiple times

Issue: -

## Description

Code duplication makes maintenance more difficult, so it can be better to replace the multiple occurrences with a constant.

#### Parameters
<table width="80%"><tr><th>Parameter</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>allowed</td>
        <td>Maximum occurences allowed</td>
        <td>integer</td>
        <td>1</td>
      </tr><tr><td>ignoreRegex</td>
        <td>Ignore regular expression</td>
        <td>string</td>
        <td>^&quot;&quot;$</td>
      </tr></table>

### Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.MultipleStringLiteralsChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;allowed&quot;&gt;1&lt;/parameter&gt;
  &lt;parameter name=&quot;ignoreRegex&quot;&gt;^\&amp;quot;\&amp;quot;$&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_NamedArgumentChecker" />

## Further Reading

* [Scalastyle - MultipleStringLiterals](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_MultipleStringLiterals)