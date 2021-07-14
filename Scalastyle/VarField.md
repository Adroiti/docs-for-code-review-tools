Pattern: Mutable field by `class`/`object`

Issue: -

## Description

vars (mutable fields) are deprecated if you're using a strict functional style.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.VarFieldChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_VarLocalChecker" />

## Further Reading

* [Scalastyle - VarField](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_VarFieldChecker)