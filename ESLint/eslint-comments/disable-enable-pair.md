Pattern: Missing use of `eslint-enable`

Issue: -

## Description

`eslint-disable` directive-comments disable ESLint rules in all lines preceded by the comment. If you forget `eslint-enable` directive-comment, you may overlook ESLint warnings unintentionally.

This rule warns `eslint-disable` directive-comments if the `eslint-enable` directive-comment for that does not exist.

Example of **incorrect** code:

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */
var foo = bar()
```

Example of **correct** code:

```js
/*eslint eslint-comments/disable-enable-pair: error */

/*eslint-disable no-undef, no-unused-vars */
var foo = bar()
/*eslint-enable no-undef, no-unused-vars */
```

## Further Reading

* [disable-enable-pair](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/disable-enable-pair.html)