Pattern: Unused expression

Issue: -

## Description

An unused expression which has no effect on the state of the program indicates a logic error.

For example, `n + 1;` is not a syntax error, but it might be a typing mistake where a programmer meant an assignment statement `n += 1;` instead. Sometimes, such unused expressions may be eliminated by some build tools in production environment, which possibly breaks application logic.

## Further Reading

* [ESLint - no-unused-expressions](https://eslint.org/docs/rules/no-unused-expressions)