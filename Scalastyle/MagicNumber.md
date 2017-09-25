Pattern: Use of magic number

Issue: -

## Description

Replacing a magic number with a named constant can make code easier to read and understand, and can avoid some subtle bugs. A simple assignment to a `val` is not considered to be a magic number, for example:

```scala
val foo = 4
```

is not a magic number, but

```scala
var foo = 4
```

is considered to be a magic number.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>ignore</td>
        <td>Ignore</td>
        <td>string</td>
        <td>-1,0,1,2</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.MagicNumberChecker" level="warning">
 <parameters>
  <parameter name="ignore">-1,0,1,2,3</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_MethodArgumentNamesChecker" />

## Further Reading

* [Scalastyle - MagicNumber](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_MagicNumberChecker)