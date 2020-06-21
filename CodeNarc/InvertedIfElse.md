Pattern: Inverted `if-else`

Issue: -

## Description

An inverted *if-else* statement is one in which there is a single `if` statement with a single `else` branch and the boolean test of the `if` is negated. For instance `if (!x) false else true`. It is usually clearer to write this as `if (x) true else false`.

## Further Reading

* [CodeNarc - InvertedIfElse](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#invertedifelse-rule)