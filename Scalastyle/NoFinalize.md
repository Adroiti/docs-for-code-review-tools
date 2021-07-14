Pattern: Defined `finalize()` method

Issue: -

## Description

`finalize()` is called when the object is garbage collected, and garbage collection is not guaranteed to happen.
 It is therefore unwise to rely on code in `finalize()` method.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NoFinalizeChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_NoWhitespaceAfterLeftBracketChecker" />

## Further Reading

* [Scalastyle - NoFinalize](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_NoFinalizeChecker)