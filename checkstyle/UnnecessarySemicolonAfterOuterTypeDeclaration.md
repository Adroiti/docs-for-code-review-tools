Pattern: Unnecessary `;` after type declaration

Issue: -

## Description

Checks if unnecessary semicolon is used after type declaration.

## Examples

```java
class A {
 // some code
 class Inner {
 }; // no violation, covered by UnnecessarySemicolonAfterTypeMemberDeclaration 
}; // violation
```

## Further Reading

* [checkstyle - UnnecessarySemicolonAfterOuterTypeDeclaration](http://checkstyle.sourceforge.net/config_coding.html#UnnecessarySemicolonAfterOuterTypeDeclaration)