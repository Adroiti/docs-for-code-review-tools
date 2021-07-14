Pattern: Missing braces in `for`

Issue: -

## Description

Usage of braces (rather than parentheses) within a `for` comprehension means that you don't have to specify a semicolon at the end of every line:

```scala
for {      // braces
  t <- List(1,2,3)
  if (i % 2 == 0)
} yield t

is preferred to

for (      // parentheses
  t <- List(1,2,3);
  if (i % 2 == 0)
) yield t
```

To fix it, replace the () with {}. And then remove the ; at the end of the lines.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ForBraceChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_IfBraceChecker" />

## Further Reading

* [Scalastyle - ForBrace](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ForBraceChecker)