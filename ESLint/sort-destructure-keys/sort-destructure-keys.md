Pattern: Unsorted object destructure keys

Issue: -

## Description

Require object destructure keys to be sorted.

Example of incorrect code for the `{"caseSensitive": true}` option:

```js
let { a, B, c } = obj;
```

Example of correct code for the `{"caseSensitive": true}` option:

```js
let { B, a, c } = obj;
```

## Further Reading

* [ eslint-plugin-sort-destructure-keys](https://github.com/mthadley/eslint-plugin-sort-destructure-keys)