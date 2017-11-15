Pattern: Missing `key` prop for element

Issue: -

## Description

Warns for missing `key` props in JSX element array literals and inside return statements of `Array.prototype.map` callbacks.

Example of **incorrect** code:

```ts
[1, 2, 3].map(function(x) { return <App /> });
                                   ~~~~~~~
```

Example of **correct** code:

```ts
[1, 2, 3].map(function(x) { return <App key={x} /> });
```