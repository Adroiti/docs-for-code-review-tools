Pattern: Unused `eslint-enable`

Issue: -

## Description

This rule warns `eslint-enable` directive-comments which have no effect.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-unused-enable: error */

/*eslint-disable no-undef */
doSomething()
/*eslint-enable no-undef-init */
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-unused-enable: error */

/*eslint-disable no-undef */
doSomething()
/*eslint-enable no-undef */
```

## Further Reading

* [no-unused-enable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-unused-enable.html)