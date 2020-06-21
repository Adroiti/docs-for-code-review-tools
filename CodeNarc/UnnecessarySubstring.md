Pattern: Unnecessary `String.substring()`

Issue: -

## Description

This rule finds usages of `String.substring(int)` and `String.substring(int, int)` that can be replaced by use of the `subscript` operator. For instance, `var.substring(5)` can be replaced with `var[5..-1]`.

Note that the `String.substring(beginIndex,endIndex)` method specifies a range of `beginIndex..endIndex-1`, while Groovy's String subscript specifies an inclusive range. So, `"123456".substring(1, 5)` is equivalent to `"123456"[1..4]`.

Example of violations:

``` groovy
someVar.substring(5)          // can use someVar[5..-1] instead
someVar.substring(1, 5)       // can use someVar[1..4] instead
```

## Further Reading

* [CodeNarc - UnnecessarySubstring](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarysubstring-rule)