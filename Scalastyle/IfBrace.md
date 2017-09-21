Pattern: `if` without braces

Issue: -

## Description

Some people find if clauses with braces easier to read. The `singleLineAllowed` property allows if constructions of the type:

    if (bool_expression) expression1 else expression2

The `doubleLineAllowed` property allows if constructions of the type:

    if (bool_expression) expression1
    else expression2

Note: If you intend to enable only if expressions in the format below, disable the `IfBraceChecker` altogether.

    if (bool_expression)
      expression1
    else
      expression2

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>singleLineAllowed</td>
        <td>Single Line Allowed</td>
        <td>boolean</td>
        <td>true</td>
      </tr><tr><td>doubleLineAllowed</td>
        <td>Double Line Allowed</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.IfBraceChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;singleLineAllowed&quot;&gt;true&lt;/parameter&gt;
  &lt;parameter name=&quot;doubleLineAllowed&quot;&gt;false&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_IllegalImportsChecker" />

## Further Reading

* [Scalastyle - IfBrace](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_IfBraceChecker)