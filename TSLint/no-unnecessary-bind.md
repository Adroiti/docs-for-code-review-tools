Pattern: Unnecessary bind

Issue: -

## Description

Deprecated - This rule is in the TSLint product as `unnecessary-bind`.

Do not bind 'this' as the context for a function literal or lambda
expression. If you bind 'this' as the context to a function literal,
then you should just use a lambda without the bind. If you bind 'this'
as the context to a lambda, then you can remove the bind call because
'this' is already the context for lambdas. Works for Underscore methods
as well.

## Further Reading

* [TSLint - no-unnecessary-bind](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)