Pattern: Wrong import order

Issue: -

## Description

Consistent import ordering improves code readability and reduces unrelated changes in patches.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ImportOrderChecker" level="warning">
 <parameters>
  <parameter name="groups">java,scala,others</parameter>
  <parameter name="group.java">javax?\..+</parameter>
  <parameter name="group.scala">scala\..+</parameter>
  <parameter name="group.others">.+</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_LowercasePatternMatchChecker" />

## Further Reading

* [Scalastyle - ImportOrder](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ImportOrderChecker)