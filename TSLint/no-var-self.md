Pattern: Use of `var self = this`

Issue: -

## Description

Deprecated - This rule can be replaced with TSLint's `no-this-assignment`.

Do not use `var self = this`; instead, manage scope with arrow
functions/lambdas. Self variables are a common practice in JavaScript
but can be avoided in TypeScript. By default the rule bans any
assignments of the `this` reference. If you want to enforce a naming
convention or allow some usages then configure the rule with a regex. By
default the rule is configured with `(?!)` which matches nothing. You
can pass `^self$` to allow variables named self or pass `^(?!self$)` to
allow anything other than self, for example.

## Further Reading

* [TSLint - no-var-self](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)