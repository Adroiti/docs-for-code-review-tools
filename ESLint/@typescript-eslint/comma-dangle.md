Pattern: Inconsistent trailing comma

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent use of trailing commas in object and array literals, which can now be configured using the stylistic plugin's comma-dangle rule.

## Examples

Example of **incorrect** code:
```ts
const obj = {
  foo: 'foo',
  bar: 'bar'  // missing trailing comma
};

type Props = {
  name: string,
  age: number  // missing trailing comma
};

const arr = [
  1,
  2,
  3  // missing trailing comma
];
```

Example of **correct** code:
```ts
const obj = {
  foo: 'foo',
  bar: 'bar',
};

type Props = {
  name: string,
  age: number,
};

const arr = [
  1,
  2,
  3,
];
```

See [eslint.style](https://eslint.style) for the current version of this rule.