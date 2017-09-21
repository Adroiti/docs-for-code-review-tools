Pattern: Defined `finalize()` method

Issue: -

## Description

`finalize()` is called when the object is garbage collected, and garbage collection is not guaranteed to happen.
 It is therefore unwise to rely on code in `finalize()` method.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.NoFinalizeChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_NoWhitespaceAfterLeftBracketChecker" />

## Further Reading

* [Scalastyle - NoFinalize](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NoFinalizeChecker)