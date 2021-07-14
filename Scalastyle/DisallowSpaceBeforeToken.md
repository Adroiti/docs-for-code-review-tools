Pattern: Whitespace before token

Issue: -

## Description

Correct formatting can help readability.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.DisallowSpaceBeforeTokenChecker" level="warning">
 <parameters>
  <parameter name="tokens">COLON, COMMA, RPAREN</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_EmptyClassChecker" />

## Further Reading

* [Scalastyle - DisallowSpaceBeforeToken](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_DisallowSpaceBeforeTokenChecker)