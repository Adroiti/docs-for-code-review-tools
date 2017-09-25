Pattern: Use of structural type

Issue: -

## Description

Structural types are implemented with reflection at runtime, and are inherently less performant than nominal types. Your should prefer the use of nominal types, unless structural types provide a clear benefit.

Warning: This rule can also wrongly pick up type lamdbas and other such constructs. This rule should be used with care. You always have the alternative of the `scalac` checking for structural types.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.StructuralTypeChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_TodoCommentChecker" />

## Further Reading

* [Scalastyle - StructuralType](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_StructuralTypeChecker)
* [The Scala Programming Language - Structural Types](https://docs.scala-lang.org/style/types.html#structural-types)