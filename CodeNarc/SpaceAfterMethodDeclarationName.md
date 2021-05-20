Pattern: Use of space after method declaration name

Issue: -

## Description

Checks whether method declarations do not contain unnecessary whitespace between method name and the opening parenthesis for parameter list.

## Examples

```java
class ClassWithWhitespaceInConstructorDeclaration {
	
	ClassWithWhitespaceInConstructorDeclaration () { //violation
	}
	
	void methodWithWhitespaceInDeclaration () { //violation
	}
}
```

## Further Reading

* [CodeNarc - SpaceAfterMethodDeclarationName](https://codenarc.org/codenarc-rules-formatting.html#spaceaftermethoddeclarationname-rule)