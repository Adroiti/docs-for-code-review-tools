Pattern: Missing use of braces for `while`

Issue: -

## Description

While cannot be used in a pure-functional manner, that's why it's recommended to never omit braces according to Scala Style Guide.

### Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.WhileBraceChecker" level="warning"/>
```

## Further Reading

* [Scalastyle - WhileBrace](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_WhileBraceChecker)