Pattern: Use of directive-comment

Issue: -

## Description

Abuse of directive-comments may cause to overlook bugs or upset of coding style. This rule disallows a use of directive-comments.	

Example of **incorrect** code:

```js
/*eslint eslint-comments/no-use: error */

/* eslint no-undef: off */
/* eslint-env browser */
/* eslint-disable foo */
/* eslint-enable bar */
// eslint-disable-line
// eslint-disable-next-line
/* exported foo */
/* global $ */
/* globals a, b, c */

```

## Further Reading

* [no-use](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/no-use.html)