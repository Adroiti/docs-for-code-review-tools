Pattern: Use of `throw`

Issue: -

## Description

`throw` statements should be replaced with type-safe error constructs like `Try` and `Either`, which communicate the possibility of error in the type signature.

### Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ThrowChecker" level="warning"/>
```
## Further Reading

* [Scalastyle - Throw](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ThrowChecker)