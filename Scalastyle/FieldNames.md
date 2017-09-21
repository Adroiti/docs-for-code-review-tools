Pattern: Invalid field name

Issue: -

## Description

A consistent naming convention for field names can make code easier to read and understand.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[a-z][A-Za-z0-9]*$</td>
      </tr><tr><td>objectFieldRegex</td>
        <td>Regular expression for constants</td>
        <td>string</td>
        <td>^[A-Z][A-Za-z0-9]*$</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.FieldNamesChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[a-z][A-Za-z0-9]*$&lt;/parameter&gt;
  &lt;parameter name=&quot;objectFieldRegex&quot;&gt;^[A-Z][A-Za-z0-9]*$&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_ForBraceChecker" />

## Further Reading

* [Scalastyle - FieldNames](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_FieldNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#constants-values-variable-and-methods)