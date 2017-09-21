Pattern: Wrong import order

Issue: -

## Description

Consistent import ordering improves code readability and reduces unrelated changes in patches.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.ImportOrderChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;groups&quot;&gt;java,scala,others&lt;/parameter&gt;
  &lt;parameter name=&quot;group.java&quot;&gt;javax?\..+&lt;/parameter&gt;
  &lt;parameter name=&quot;group.scala&quot;&gt;scala\..+&lt;/parameter&gt;
  &lt;parameter name=&quot;group.others&quot;&gt;.+&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_LowercasePatternMatchChecker" />

## Further Reading

* [Scalastyle - ImportOrder](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ImportOrderChecker)