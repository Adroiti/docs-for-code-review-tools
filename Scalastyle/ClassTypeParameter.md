Pattern: Invalid class type parameter name

Issue: -

## Description

Scala generic type names are generally single upper case letters (from the English alphabet). Note that this rule only checks the innermost type parameter to allow for `List[T]`.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[A-Z_]$</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.ClassTypeParameterChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[A-Z_]$&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_CovariantEqualsChecker" />

## Further Reading

* [Scalastyle - ClassTypeParameter](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ClassTypeParameterChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#type-parameters-generics)