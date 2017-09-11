Pattern: Unexpected label on statement

Issue: -

## Description

This rule enforces labels to be on `do/for/while/switch` statements only.
  
Rationale: Labels in JavaScript only can be used in conjunction with `break` or `continue`, constructs meant to be used for loop flow control. While you can theoretically use labels on any block statement in JS, it is considered poor code structure to do so.

## Further Reading

* [TSLint - label-position](https://palantir.github.io/tslint/rules/label-position)