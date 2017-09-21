Pattern: Illegal token

Issue: -

## Description

This rule reports issues captured with a regular expression token.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^$</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.TokenChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;regex&quot;&gt;^[ai]sInstanceOf$&lt;/parameter&gt;
 &lt;/parameters&gt;
 &lt;customMessage&gt;Avoid casting.&lt;/customMessage&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_UnderscoreImportChecker" />

## Further Reading

* [Scalastyle - Token](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_TokenChecker)