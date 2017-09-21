Pattern: Whitespace before token

Issue: -

## Description

Correct formatting can help readability.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.DisallowSpaceBeforeTokenChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;tokens&quot;&gt;COLON, COMMA, RPAREN&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_EmptyClassChecker" />

## Further Reading

* [Scalastyle - DisallowSpaceBeforeToken](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_DisallowSpaceBeforeTokenChecker)