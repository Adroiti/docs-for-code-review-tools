Pattern: Use of restricted `eslint-disable`

Issue: -

## Description

This rule warns `eslint-disable` directive-comments if the comment disable specific rules.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-restricted-disable: [error, no-undef, no-unused-vars]*/

/*eslint-disable no-undef */
f()
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-restricted-disable: [error, no-undef, no-unused-vars]*/

f() //eslint-disable-line another-rule
```

## Further Reading

* [no-restricted-disable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-restricted-disable.html)