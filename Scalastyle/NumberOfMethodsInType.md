Pattern: Too many methods in type

Issue: -

## Description

If a type declares too many methods, this can be an indication of bad design.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>maxMethods</td>
        <td>Maximum methods</td>
        <td>integer</td>
        <td>30</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.NumberOfMethodsInTypeChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;maxMethods&quot;&gt;30&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_NumberOfTypesChecker" />

## Further Reading

* [Scalastyle - NumberOfMethodsInType](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NumberOfMethodsInTypeChecker)