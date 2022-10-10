Pattern: Unnecessary `break`

Issue: -

## Description

This rule warns on useless `break` statements in case clauses of switch and select statements. GO, unlike other programming languages like C, only executes statements of the selected case while ignoring the subsequent case clauses.
Therefore, inserting a `break` at the end of a case clause has no effect.

Because `break` statements are rarely used in case clauses, when switch or select statements are inside a for-loop, the programmer might wrongly assume that a `break` in a case clause will take the control out of the loop.
The rule emits a specific warning for such cases.

## Further Reading

* [Revive - useless-break](https://revive.run/r#useless-break)