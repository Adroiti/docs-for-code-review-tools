Pattern: Use of letter `l` (ell) as suffix

Issue: -

## Description

The suffix `L` is preferred, because the letter `l` (ell) is often hard to distinguish from the digit `1` (one).

## Default configuration

```xml
<module name="UpperEll"/>
```

## Examples

Example of **incorrect** code:

```java
long number = 1234567891l;
```

Example of **correct** code:

```java
long number = 1234567891L;
```

## Further Reading

* [Java Language Specification - Integer Literals](http://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.10.1)
* [Google Java Style Guide - Numeric Literals](https://google.github.io/styleguide/javaguide.html#s4.8.8-numeric-literals)
* [checkstyle - UpperEll](https://checkstyle.sourceforge.io/checks/misc/upperell.html#UpperEll)
