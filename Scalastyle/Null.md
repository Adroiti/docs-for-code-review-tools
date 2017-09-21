Pattern: Use of `null`

Issue: -

## Description

Scala discourages use of `null`, preferring `Option`.

Note, for performance sensitive code, prefer `null` over `Option`, in order to avoid virtual method calls and boxing. Label the nullable fields clearly with Nullable.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>allowNullChecks</td>
        <td>Allow null checks</td>
        <td>boolean</td>
        <td>true</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.NullChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;allowNullChecks&quot;&gt;true&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_NumberOfMethodsInTypeChecker" />

## Further Reading

* [Scalastyle - Null](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NullChecker)