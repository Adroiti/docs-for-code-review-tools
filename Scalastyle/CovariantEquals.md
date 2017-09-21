Pattern: Covariant equals without overriding `equals(java.lang.Object)`

Issue: -

## Description

Mistakenly defining a covariant `equals()` method without overriding `equals(java.lang.Object)` can produce unexpected runtime behaviour.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.CovariantEqualsChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_CyclomaticComplexityChecker" />

## Further Reading

* [Scalastyle - CovariantEquals](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_CovariantEqualsChecker)