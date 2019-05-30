Pattern: Wrong shorthand property order

Issue: -

## Description

By convention and for better readability, shorthand properties should precede regular property declarations.

Not passing:

```ts
let obj = {
  foo: foo,
  bar,
  baz: baz,
};
```

Passing:

```ts
let obj = {
  bar,
  foo: foo,
  baz: baz,
};
```

## Further Reading

* [TSLint - object-shorthand-properties-first](https://github.com/ajafff/tslint-consistent-codestyle/blob/master/docs/object-shorthand-properties-first.md)