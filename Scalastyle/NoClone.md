Pattern: Use of `clone()` method

Issue: -

## Description

The clone method is difficult to get right. You can use the copy constructor of case classes rather than implementing clone.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NoCloneChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_NoFinalizeChecker" />

## Further Reading

* [Scalastyle - NoClone](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_NoCloneChecker)