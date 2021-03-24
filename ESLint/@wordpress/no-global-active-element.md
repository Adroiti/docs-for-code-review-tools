Pattern: Accessing active element with global

Issue: -

## Description

Avoid accessing the active element with a global. Use the `ownerDocument` property on a node ref instead.

Example of **incorrect** code:

```js
document.activeElement;
```

Example of **correct** code:

```js
ownerDocument.activeElement;
```

## Further Reading

* [GitHub - no-global-active-element](https://github.com/WordPress/gutenberg/blob/trunk/packages/eslint-plugin/rules/no-global-active-element.js)