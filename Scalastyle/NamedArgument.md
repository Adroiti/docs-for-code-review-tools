Pattern: Nameless argument literal

Issue: -

## Description

Nameless literals make code harder to understand (consider `updateEntity(1, true)` and `updateEntity(id = 1, enabled = true)`).

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>checkString</td>
        <td>Check string literals</td>
        <td>boolean</td>
        <td>false</td>
      </tr><tr><td>ignoreMethod</td>
        <td>Ignore methods by pattern</td>
        <td>string</td>
        <td>^set.+$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NamedArgumentChecker" level="warning">
 <parameters>
  <parameter name="checkString">false</parameter>
  <parameter name="ignoreMethod">^set.+$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_NoCloneChecker" />

## Further Reading

* [Scalastyle - NamedArgument](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NamedArgumentChecker)