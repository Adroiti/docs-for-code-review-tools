Pattern: Malformed JSDoc comment

Issue: -

## Description

Enforces basic format rules for JSDoc comments.

The following rules are enforced for JSDoc comments (comments starting with `/**`):

  - each line contains an asterisk and asterisks must be aligned
  - each asterisk must be followed by either a space or a newline (except for the first and the last)
  - the only characters before the asterisk on each line must be whitespace characters
  - one line comments must start with `/** ` and end with `*/`
  
Rationale: Helps maintain a consistent, readable style for JSDoc comments.

## Further Reading

* [TSLint - jsdoc-format](https://palantir.github.io/tslint/rules/jsdoc-format)