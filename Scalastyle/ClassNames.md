Pattern: Invalid class name

Issue: -

## Description

The Scala style guide recommends that class names conform to certain standards.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[A-Z][A-Za-z]*$</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.ClassNamesChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[A-Z][A-Za-z]*$&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_ClassTypeParameterChecker" />

## Further Reading

* [Scalastyle - ClassNames](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ClassNamesChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#classestraits)