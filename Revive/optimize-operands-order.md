Pattern: Unoptimized operands order

Issue: -

## Description

Conditional expressions can be written to take advantage of short circuit evaluation and speed up its average evaluation time by forcing the evaluation of less time-consuming terms before more costly ones. This rule spots logical expressions where the order of evaluation of terms seems non optimal. Please notice that confidence of this rule is low and is up to the user to decide if the suggested rewrite of the expression keeps the semantics of the original one.

## Example:

    if isGenerated(content) && !config.IgnoreGeneratedHeader {
Swap left and right side :

    if !config.IgnoreGeneratedHeader && isGenerated(content) {.

## Further Reading

* [Revive - optimize-operands-order](https://revive.run/r#optimize-operands-order)