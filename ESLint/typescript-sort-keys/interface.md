Pattern: Unsorted interface keys

Issue: -

## Description

When declaring multiple properties on an interface, some developers prefer to sort property names alphabetically to be able to find necessary property easier at the later time. Others feel that it adds complexity and becomes burden to maintain.

Examples of **incorrect** code for this rule:

```ts
/* eslint typescript-sort-keys/interface: "error" */

interface U {
  a: T
  c: T
  b: T
}
interface U {
  a: T
  c: T
  b: T
}

// Case-sensitive by default.
interface U {
  a: T
  b: T
  C: T
}

// Non-natural order by default.
interface U {
  1: T
  2: T
  10: T
}

// Non-required first order by default.
interface U {
  b?: T
  a: T
  c: T
}

interface U {
  a: T
  ['c']: T
  b: T
}
```

Examples of **correct** code for this rule:

```ts
/* eslint typescript-sort-keys/interface: "error" */

interface U {
  a: T
  b: T
  c: T
}
interface U {
  a: T
  b: T
  c: T
}

// Case-sensitive by default.
interface U {
  C: T
  a: T
  b: T
}

// Non-natural order by default.
interface U {
  1: T
  10: T
  2: T
}

// Non-required first order by default.
interface U {
  a: T
  b?: T
  c: T
}

// This rule checks computed properties which have a simple name as well.
interface U {
  a: T
  ['b']: T
  c: T
}
```


## Further Reading

* [GitHub - interface](https://github.com/infctr/eslint-plugin-typescript-sort-keys/blob/HEAD/docs/rules/interface.md)