Pattern: Use of `Optional` as field type

Issue: -

## Description

Do not use an `Optional` as a field type.

Examples:

```groovy
class MyClass {
	Optional<Integer> count;                            // violation
	public String name;
	public Optional<String> alias = Optional.of("x")    // violation
	protected static Optional<Object> lock              // violation
}
```

## Further Reading

* [CodeNarc - OptionalField](https://codenarc.org/codenarc-rules-design.html#optionalfield-rule)