Pattern: Unnecessary `;` after type member declaration

Issue: -

## Description

Checks if unnecessary semicolon is used after type member declaration.

## Examples

```java
class A {
    ; // violation, standalone semicolon
    {}; // violation, extra semicolon after init block
    static {}; // violation, extra semicolon after static init block
    A(){}; // violation, extra semicolon after constructor definition
    void method() {}; // violation, extra semicolon after method definition
    int field = 10;; // violation, extra semicolon after field declaration
}
   
```

## Further Reading

* [checkstyle - JavadocParagraph](https://checkstyle.sourceforge.io/config_coding.html#UnnecessarySemicolonAfterTypeMemberDeclaration)
