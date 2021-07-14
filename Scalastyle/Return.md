Pattern: Use of `return`

Issue: -

## Description

Use of `return` is not usually necessary in Scala. In fact, use of `return` can discourage a functional style of programming.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ReturnChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_ScalaDocChecker" />

## Further Reading

* [Scalastyle - Return](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ReturnChecker)