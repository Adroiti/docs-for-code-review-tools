Pattern: Use of tautology expression

Issue: -

## Description

Enforces that relational/equality binary operators does not take two equal variables/literals as operands. Expression like `3 === 3`, `someVar === someVar`, `“1” > “1”` are either a tautology or contradiction, and will produce an error.  
  
Rationale: clean redundant code and unnecessary comparison of objects and literals.

## Further Reading

* [TSLint - no-tautology-expression](https://palantir.github.io/tslint/rules/no-tautology-expression)