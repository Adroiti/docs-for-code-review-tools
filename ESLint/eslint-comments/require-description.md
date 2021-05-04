Pattern: Use of directive comment without description

Issue: -

## Description

This rule warns directive comments without description.

Example of **incorrect** code:

```js
/*eslint eslint-comments/require-description: error */

/* eslint no-undef: off */
/* eslint-env browser */
/* eslint-disable eqeqeq */
/* eslint-enable eqeqeq */
// eslint-disable-line
// eslint-disable-next-line
/* exported foo */
/* global $ */
/* globals a, b, c */

```

Example of **correct** code:

```js
/*eslint eslint-comments/require-description: error -- If you use directive comments, you should explain why you use them. */

/* eslint no-undef: off -- Here's a description about why this directive-comment is necessary. */
/* eslint-env browser -- This script works in browser. */
// eslint-disable-next-line -- Temporarily avoids the lint error problem. See issue XXX.
/* global $ -- This script using jQuery. */

```

## Further Reading

* [require-description](https://mysticatea.github.io/eslint-plugin-eslint-comments/rules/require-description.html)