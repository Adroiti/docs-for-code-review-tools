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

* [checkstyle - UnnecessarySemicolonAfterOuterTypeDeclaration](https://checkstyle.sourceforge.io/checks/coding/unnecessarysemicolonafteroutertypedeclaration.html#UnnecessarySemicolonAfterOuterTypeDeclaration)