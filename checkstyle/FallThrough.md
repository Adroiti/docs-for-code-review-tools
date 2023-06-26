Pattern: Fall-through in `switch` statement

Issue: -

## Description

This rule enforces convention to comment any fall-throughs (multiple case statements before termination) in `switch` block. Any of the following comments that communicate the idea of fall-through is sufficient: `fallthru`, `fall through`, `fallthrough`, `falls through` and `fallsthrough` (case sensitive).

## Default configuration

```xml
<module name="FallThrough"/>
```

## Examples

Example of **incorrect** code:

```java
switch (input) {
  case 1:
  case 2:
    prepareOneOrTwo();
  case 3:
    handleOneTwoOrThree();
    break;
  default:
    handleLargeNumber(input);
}
```

Example of **correct** code:

```java
switch (input) {
  case 1:
  case 2:
    prepareOneOrTwo();
    // fall through
  case 3:
    handleOneTwoOrThree();
    break;
  default:
    handleLargeNumber(input);
}
```

## Further Reading

* [Google Java Style Guide - Switch statements](https://google.github.io/styleguide/javaguide.html#s4.8.4-switch)
* [checkstyle - FallThrough](https://checkstyle.sourceforge.io/checks/coding/fallthrough.html#FallThrough)
