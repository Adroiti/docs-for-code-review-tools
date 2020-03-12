Pattern: Trailing comma in enum definition

Issue: -

## Description

Checks that enum definition does not contain a trailing comma. Rationale: JLS allows trailing commas in arrays and enumerations, but does not allow them in other locations. To unify the coding style, the use of trailing commas should be prohibited.

```java
enum Foo1 {
  FOO,
  BAR;
}
```

The check demands that there should not be any comma after last constant in enum definition.

```java
enum Foo1 {
  FOO,
  BAR, //violation
}
```

## Examples

```java
num Foo1 {
  FOO,
  BAR; //OK
}
enum Foo2 {
  FOO,
  BAR //OK
}
enum Foo3 {
  FOO,
  BAR, //violation
}
enum Foo4 {
  FOO,
  BAR, // violation
  ;
}
enum Foo5 {
  FOO,
  BAR,; // violation
}
enum Foo6 { FOO, BAR,; } // violation
enum Foo7 { FOO, BAR, } // violation
enum Foo8 {
  FOO,
  BAR // OK
  ;
}
enum Foo9 { FOO, BAR; } // OK
enum Foo10 { FOO, BAR } // OK
```

## Further Reading

* [checkstyle - NoEnumTrailingComma](http://checkstyle.sourceforge.net/config_coding.html#NoEnumTrailingComma)