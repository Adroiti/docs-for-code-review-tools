Pattern: Invalid method name

Issue: -

## Description

The Scala style guide recommends that method names conform to certain standards. Use the `ignoreOverride` parameter if overridden method cannot be changed.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z0-9]*(_=)?$</td>
      </tr><tr><td>ignoreRegex</td>
        <td>Regular expression to ignore</td>
        <td>string</td>
        <td>^$</td>
      </tr><tr><td>ignoreOverride</td>
        <td>Ignore override</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.MethodNamesChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[A-Za-z]*$&lt;/parameter&gt;
  &lt;parameter name=&quot;ignoreRegex&quot;&gt;^.*$&lt;/parameter&gt;
  &lt;parameter name=&quot;ignoreOverride&quot;&gt;false&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_MultipleStringLiteralsChecker" />

## Further Reading

* [Scalastyle - MethodNames](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_MethodNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#methods)