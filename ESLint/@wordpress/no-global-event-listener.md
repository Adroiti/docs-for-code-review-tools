Pattern: Use of global `EventListener`

Issue: -

## Description

Avoid using (add|remove)EventListener with globals. Use `ownerDocument` or `ownerDocument.defaultView` on a node ref instead.

Example of **incorrect** code:

```js
document.addEventListener();
document.removeEventListener();
```

Example of **correct** code:

```js
ownerDocument.addEventListener();
ownerDocument.removeEventListener();
```

## Further Reading

* [GitHub - no-global-event-listener](https://github.com/WordPress/gutenberg/blob/trunk/packages/eslint-plugin/rules/no-global-event-listener.js)