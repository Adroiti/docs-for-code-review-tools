Pattern: Mutable variable by function

Issue: -

## Description

vars (mutable local variables) loops are deprecated if you're using a strict functional style.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.VarLocalChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_WhileChecker" />

## Further Reading

* [Scalastyle - VarLocal](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_VarLocalChecker)