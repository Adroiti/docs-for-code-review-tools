Pattern: Trailing comma in array initialization

Issue: -

## Description

Checks that array initialization do not contain a trailing comma. Rationale: JLS allows trailing commas in arrays and enumerations, but does not allow them in other locations. To unify the coding style, the use of trailing commas should be prohibited.

```java
int[] foo = new int[] {
  1,
  2
};
```

The check demands that there should not be any comma after the last element of an array.

```java
String[] foo = new String[] {
  "FOO",
  "BAR", //violation
}
```

## Examples

```java
String[] foo1 = {
  "FOO", // OK
  "BAR", // violation
};
String[] foo2 = { "FOO", "BAR", }; // violation
String[] foo3 = {
  "FOO", // OK
  "BAR" // OK
};
String[] foo4 = { "FOO", "BAR" }; // OK
```

## Further Reading

* [checkstyle - NoArrayTrailingComma](http://checkstyle.sourceforge.net/config_coding.html#NoArrayTrailingComma)