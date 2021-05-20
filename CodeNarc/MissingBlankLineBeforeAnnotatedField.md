Pattern: Missing blank line before annotated field

Issue: -

## Description

Checks that there is a blank line before a field declaration that uses annotations. Ignore field declarations where all annotations are on the same line as the field declaration.

## Examples

```java
class MyClass {
	// No violations for field declarations preceded by a comment
	@Delegate
	AutoCloseable stream
	
	String publicField                  // violation
	@PackageScope
	String packageScopedField
}
```

## Further Reading

* [CodeNarc - MissingBlankLineBeforeAnnotatedField](https://codenarc.org/codenarc-rules-formatting.html#missingblanklinebeforeannotatedfield-rule)