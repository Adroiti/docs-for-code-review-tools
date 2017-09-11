Pattern: Restricted type in boolean expression

Issue: -

## Description

Restricts the types allowed in boolean expressions. By default only booleans are allowed.

The following nodes are checked:

  - Arguments to the `!`, `&&`, and `||` operators
  - The condition in a conditional expression (`cond ? x : y`)
  - Conditions for `if`, `for`, `while`, and `do-while` statements.

## Further Reading

* [TSLint - strict-boolean-expressions](https://palantir.github.io/tslint/rules/strict-boolean-expressions)