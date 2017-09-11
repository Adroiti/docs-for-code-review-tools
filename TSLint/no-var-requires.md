Pattern: Use of `require`

Issue: -

## Description

Disallows the use of `require` statements except in import statements.

In other words, the use of forms such as `var module = require("module")` are banned. Instead use ES6 style imports or `import foo = require('foo')` imports.

## Further Reading

* [TSLint - no-var-requires](https://palantir.github.io/tslint/rules/no-var-requires)