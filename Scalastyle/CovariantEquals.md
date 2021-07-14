Pattern: Covariant equals without overriding `equals(java.lang.Object)`

Issue: -

## Description

Mistakenly defining a covariant `equals()` method without overriding `equals(java.lang.Object)` can produce unexpected runtime behaviour.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.CovariantEqualsChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_CyclomaticComplexityChecker" />

## Further Reading

* [Scalastyle - CovariantEquals](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_CovariantEqualsChecker)