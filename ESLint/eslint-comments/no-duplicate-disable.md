Pattern: Duplicate `eslint-disable`

Issue: -

## Description

Duplicate of `eslint-disable` directive-comments implies that there is a mix of wide-range directive-comments and narrow-range directive-comments. The mix may cause to overlook ESLint warnings in future.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-duplicate-disable: error */

/*eslint-disable no-undef */

var foo = bar() //eslint-disable-line no-undef
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-duplicate-disable: error */

/*eslint-disable no-undef */

var foo = bar()
```

## Further Reading

* [no-duplicate-disable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-duplicate-disable.html)