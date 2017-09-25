Pattern: Inferred method with explicit return type

Issue: -

## Description

A public method declared on a type is effectively an API declaration. Explicitly declaring a return type means that other code which depends on that type won't break unexpectedly.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>ignoreOverride</td>
        <td>Ignore overridden methods</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.PublicMethodsHaveTypeChecker" level="warning">
 <parameters>
  <parameter name="ignoreOverride">false</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_RedundantIfChecker" />

## Further Reading

* [Scalastyle - PublicMethodsHaveType](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_PublicMethodsHaveTypeChecker)