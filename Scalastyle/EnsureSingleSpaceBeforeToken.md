Pattern: Missing single space before token

Issue: -

## Description

Correct formatting can help readability.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.EnsureSingleSpaceBeforeTokenChecker" level="warning">
 <parameters>
  <parameter name="tokens">LPAREN</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_EqualsHashCodeChecker" />

## Further Reading

* [Scalastyle - EnsureSingleSpaceBeforeToken](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_EnsureSingleSpaceBeforeTokenChecker)