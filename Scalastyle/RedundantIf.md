Pattern: Redundant `if`

Issue: -

## Description

If expressions with boolean constants in both branches can be eliminated without affecting readability. Prefer simply `cond` to `if (cond) true else false` and `!cond` to `if (cond) false else true`.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.RedundantIfChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_ReturnChecker" />

## Further Reading

* [Scalastyle - RedundantIf](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_RedundantIfChecker)