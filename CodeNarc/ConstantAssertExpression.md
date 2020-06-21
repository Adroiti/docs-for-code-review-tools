Pattern: Constant `assert` expression

Issue: -

## Description

Checks for *assert* statements with a constant value for the *assert* boolean expression, such as `true`, `false`, `null`, or a literal constant value. These *assert* statements will always pass or always fail, depending on the constant/literal value. Examples of violations include:

``` groovy
assert true
assert false, "assertion message"
assert Boolean.TRUE
assert Boolean.FALSE
assert null
assert 0
assert 99.7
assert ""
assert "abc"
assert [:]
assert [a:123, b:456]
assert [a, b, c]
```

## Further Reading

* [CodeNarc - ConstantAssertExpression](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#constantassertexpression-rule)