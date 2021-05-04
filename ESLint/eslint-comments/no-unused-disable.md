Pattern: Unused `eslint-disable`

Issue: -

## Description

Since refactoring or a bug fix of upstream, an `eslint-disable` directive-comment may become unnecessary. In that case, you should remove it since it may cause to overlook ESLint warnings in future.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-unused-disable: error, eqeqeq: error, no-undef: error */

var foo = bar() //eslint-disable-line no-undef,eqeqeq
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-unused-disable: error, eqeqeq: error, no-undef: error */

var foo = bar() //eslint-disable-line no-undef
```

## Further Reading

* [no-unused-disable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-unused-disable.html)