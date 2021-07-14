Pattern: Invalid class type parameter name

Issue: -

## Description

Scala generic type names are generally single upper case letters (from the English alphabet). Note that this rule only checks the innermost type parameter to allow for `List[T]`.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>regex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^[A-Z_]$</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ClassTypeParameterChecker" level="warning">
 <parameters>
  <parameter name="regex">^[A-Z_]$</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_CovariantEqualsChecker" />

## Further Reading

* [Scalastyle - ClassTypeParameter](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ClassTypeParameterChecker)
* [The Scala Programming Language - Naming Conventions](https://docs.scala-lang.org/style/naming-conventions.html#type-parameters-generics)