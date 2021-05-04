Pattern: Use of aggregating `eslint-enable`

Issue: -

## Description

`eslint-enable` directive-comments can enable rules which are disabled by different `eslint-disable` directive-comments. It can enable a rule unintentionally.

This rule warns `eslint-enable` directive-comments which enable rules for multiple `eslint-disable` directive-comments.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-aggregating-enable: error*/

/*eslint-disable no-undef */
f()
/*eslint-disable no-var */
var a
/*eslint-enable */
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-aggregating-enable: error*/

/*eslint-disable no-undef */
f()
/*eslint-disable no-var */
var a
/*eslint-enable no-var */

/*eslint-enable no-undef */
```

## Further Reading

* [no-aggregating-enable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-aggregating-enable.html)