Pattern: Inconsistent spacing around object keys

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing around object literal keys and their colons, which can now be configured using the stylistic plugin's key-spacing rule.

## Examples

Example of **incorrect** code:
```ts
const obj = {
  foo:42,
  bar :  33,
  baz:  {
    qux:2
  }
};

type Props = {
  name :string,
  age:  number
};
```

Example of **correct** code:
```ts
const obj = {
  foo: 42,
  bar: 33,
  baz: {
    qux: 2
  }
};

type Props = {
  name: string,
  age: number
};
```

See [eslint.style](https://eslint.style) for the current version of this rule.