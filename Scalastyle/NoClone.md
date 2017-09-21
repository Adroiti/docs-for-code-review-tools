Pattern: Use of `clone()` method

Issue: -

## Description

The clone method is difficult to get right. You can use the copy constructor of case classes rather than implementing clone.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.NoCloneChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_NoFinalizeChecker" />

## Further Reading

* [Scalastyle - NoClone](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NoCloneChecker)