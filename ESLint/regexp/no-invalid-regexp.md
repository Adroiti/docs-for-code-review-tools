Pattern: Invalid expression in `RegExp` constructor

Issue: -

## Description

This rule reports invalid regular expression patterns given to `RegExp` constructors.

This rule is almost functionally equivalent to ESLint's `no-invalid-regexp` rule. The only difference is that this rule doesn't validate flags. The main benefits are better error reporting and better support for complex constructor calls.

## Examples

```js
/* eslint regexp/no-invalid-regexp: "error" */
/* ✓ GOOD */
RegExp('foo')
RegExp('[a' + ']')

/* ✗ BAD */
RegExp('\\')
RegExp('[a-Z]*')
RegExp('\\p{Foo}', 'u')

const space = '\\s*'
RegExp('=' + space + '+(\\w+)', 'u')
```
