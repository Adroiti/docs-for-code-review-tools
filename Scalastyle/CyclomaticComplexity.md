Pattern: Cyclomatic complexity is too high

Issue: -

## Description

If the code is too complex, then this can make code hard to read.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maximum</td>
        <td>Maximum</td>
        <td>integer</td>
        <td>10</td>
      </tr><tr><td>countCases</td>
        <td>Count Cases</td>
        <td>boolean</td>
        <td>true</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.CyclomaticComplexityChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;maximum&quot;&gt;10&lt;/parameter&gt;
  &lt;parameter name=&quot;countCases&quot;&gt;true&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_DeprecatedJavaChecker" />

## Further Reading

* [Scalastyle - CyclomaticComplexity](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_CyclomaticComplexityChecker)