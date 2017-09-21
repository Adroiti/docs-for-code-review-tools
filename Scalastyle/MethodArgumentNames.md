Pattern: Invalid method argument name

Issue: -

## Description

The Scala style guide recommends that method argument names conform to certain standards.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z0-9]*$</td>
      </tr><tr><td>ignoreRegex</td>
        <td>Regular expression to ignore</td>
        <td>string</td>
        <td>^$</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.MethodArgumentNamesChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[a-z][A-Za-z0-9]*$&lt;/parameter&gt;
  &lt;parameter name=&quot;ignoreRegex&quot;&gt;^$&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_MethodLengthChecker" />

## Further Reading

* [Scalastyle - MethodArgumentNames](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_MethodArgumentNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#methods)