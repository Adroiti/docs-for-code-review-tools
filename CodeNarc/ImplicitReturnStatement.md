Pattern: Implicit return statement

Issue: -

## Description

Checks for methods that are missing an explicit return statement.

This rule skips void methods and def (dynamic return type) methods, as well as methods whose last statement is a:

- throw
- if
- for
- while
- do .. while
- switch
- try/catch

## Examples

``` groovy
boolean example() { true }          // violation

protected int longerExample() {
	if (baseName == null) {
		return 0
	}
	99                              // violation
}
```

## Further Reading

* [CodeNarc - ImplicitReturnStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#implicitreturnstatement-rule)