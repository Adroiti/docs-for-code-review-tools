Pattern: Constant `if` expression

Issue: -

## Description

Checks for *if* statements with a constant value for the *if* boolean expression, such as `true`, `false`, `null`, or a literal constant value. These *if* statements can be simplified or avoided altogether. Examples of violations include:

``` groovy
if (true) { .. }
if (false) { .. }
if (Boolean.TRUE) { .. }
if (Boolean.FALSE) { .. }
if (null) { .. }
if (0) { .. }
if (99.7) { .. }
if ("") { .. }
if ("abc") { .. }
if ([:]) { .. }
if ([a:123, b:456]) { .. }
if ([a, b, c]) { .. }
```

## Further Reading

* [CodeNarc - ConstantIfExpression](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#constantifexpression-rule)