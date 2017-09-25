Pattern: Missing single space after token

Issue: -

## Description

Correct formatting can help readability.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.EnsureSingleSpaceAfterTokenChecker" level="warning">
 <parameters>
  <parameter name="tokens">COLON, IF</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_EnsureSingleSpaceBeforeTokenChecker" />

## Further Reading

* [Scalastyle - EnsureSingleSpaceAfterToken](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_EnsureSingleSpaceAfterTokenChecker)