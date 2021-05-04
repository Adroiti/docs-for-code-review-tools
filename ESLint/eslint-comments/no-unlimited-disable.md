Pattern: Unlimited `eslint-disable`

Issue: -

## Description

`eslint-disable` directive-comments disable all rules by default. This may cause to overlook some ESLint warnings unintentionally. So you should specify the rules to disable accurately.

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-unlimited-disable: error */

var foo; //eslint-disable-line
```

Example of **correct** code:

```js
/*eslint eslint-comments/no-unlimited-disable: error */

var foo; //eslint-disable-line no-unused-vars
```

## Further Reading

* [no-unlimited-disable](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-unlimited-disable.html)