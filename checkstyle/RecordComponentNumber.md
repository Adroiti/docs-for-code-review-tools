Pattern: Malformed record component name

Issue: -

## Description

Checks that record component names conform to a specified pattern.

## Examples

```java
record MyRecord1(String value, int other) {} // OK
record MyRecord2(String... strings) {} // OK
record MyRecord3(double myNumber) {} // violation, the record component name
                             // should match the regular expression "^[a-z]+$"
```

## Further Reading

* [checkstyle - RecordComponentNumber](https://checkstyle.sourceforge.io/checks/sizes/recordcomponentnumber.html#RecordComponentNumber)