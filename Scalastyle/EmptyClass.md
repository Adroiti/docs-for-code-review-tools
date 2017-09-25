Pattern: Redundant braces in `class`/`trait`

Issue: -

## Description

If a `class` or `trait` has no members, then braces are unnecessary, and can be removed.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.EmptyClassChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_EmptyInterpolatedStringChecker" />

## Further Reading

* [Scalastyle - EmptyClass](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_EmptyClassChecker)