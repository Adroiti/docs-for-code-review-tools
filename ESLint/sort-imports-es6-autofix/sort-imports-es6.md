Pattern: Wrong import sorting

Issue: -

## Description

A sort-imports rule that properly distinguishes between ES6 import types and that is also able to autofix all detected problems.

ESLint's built-in `sort-imports` rule considers the following to be the same type of import:

```js
import foo from 'foo';
import { bar } from 'bar';
```

This version of the rule fixes that.

## Further Reading

* [GitHub - sort-imports-es6](https://github.com/marudor/eslint-plugin-sort-imports-es6-autofix/blob/master/README.md)