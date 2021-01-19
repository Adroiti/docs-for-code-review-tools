Pattern: Missing use of `readonly` for `@Output`

Issue: -

## Description

Prefer to declare `@Output` as `readonly` since they are not supposed to be reassigned.

## Further Reading

* [TSLint - prefer-output-readonly](http://codelyzer.com/rules/prefer-output-readonly/)