Pattern: Missing braces in `for`

Issue: -

## Description

Usage of braces (rather than parentheses) within a `for` comprehension means that you don't have to specify a semicolon at the end of every line:

    for {      // braces
      t <- List(1,2,3)
      if (i % 2 == 0)
    } yield t

  is preferred to

    for (      // parentheses
      t <- List(1,2,3);
      if (i % 2 == 0)
    ) yield t

  To fix it, replace the () with {}. And then remove the ; at the end of the lines.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.ForBraceChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_IfBraceChecker" />

## Further Reading

* [Scalastyle - ForBrace](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ForBraceChecker)