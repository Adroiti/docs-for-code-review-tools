Pattern: Accessing selection with global

Issue: -

## Description

Avoid accessing the selection with a global. Use the `ownerDocument.defaultView` property on a node ref instead.

Example of **incorrect** code:

```js
window.getSelection();
```

Example of **correct** code:

```js
defaultView.getSelection();
```

## Further Reading

* [GitHub - no-global-get-selection](https://github.com/WordPress/gutenberg/blob/trunk/packages/eslint-plugin/rules/no-global-get-selection.js)