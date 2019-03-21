Pattern: Unnecessary `else`

Issue: -

## Description

Disallows `else` blocks following `if` blocks ending with a `break`, `continue`, `return`, or `throw` statement.  
  
Rationale: When an `if` block is guaranteed to exit control flow when entered, it is unnecessary to add an `else` statement. The contents that would be in the `else` block can be placed after the end of the `if` block.

## Further Reading

* [TSLint - unnecessary-else](https://palantir.github.io/tslint/rules/unnecessary-else)