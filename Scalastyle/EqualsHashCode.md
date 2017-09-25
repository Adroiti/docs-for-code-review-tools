Pattern: Missing override for `equals()` or `hashCode()`

Issue: -

## Description

Defining either `equals()` or `hashCode()` in a class without defining the other is a known source of bugs. Usually, when you define one, you should also define the other.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.EqualsHashCodeChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_FieldNamesChecker" />

## Further Reading

* [Scalastyle - EqualsHashCode](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_EqualsHashCodeChecker)