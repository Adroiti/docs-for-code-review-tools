Pattern: No code in file

Issue: -

## Description

Checks whether file contains code. Files which are considered to have no code:

- File with no text
- File with single line comment(s)
- File with a multi line comment(s).

## Examples

```java
// single line comment // violation


/* // violation
 block comment
*/
     
```

## Further Reading

* [checkstyle - NoCodeInFile](https://checkstyle.sourceforge.io/checks/misc/nocodeinfile.html#NoCodeInFile)
