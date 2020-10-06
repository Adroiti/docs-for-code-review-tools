Pattern: Use of `Optional` as parameter type for method

Issue: -

## Description

Do not use an `Optional` as a parameter type for a method or constructor.

Examples:

```groovy
class MyClass {
	protected MyClass(Optional<Integer> count) { }                  // violation
	MyClass(Optional<String> name, Optional<Integer> sum) { }       // 2 violations
	private MyClass(Optional something) { }                         // violation

	void doStuff(Optional<Integer> count) { }                       // violation
	public String getName() { return 'abc' }
	int count(Optional<String> alias, Optional<Integer> total) { }  // 2 violations
	private doSomething(Optional something) { }                     // violation
}
```

## Further Reading

* [CodeNarc - OptionalMethodParameter](https://codenarc.org/codenarc-rules-design.html#optionalmethodparameter-rule)