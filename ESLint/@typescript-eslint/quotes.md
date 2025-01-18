Pattern: Inconsistent quote style

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent use of single or double quotes for string literals, which can now be configured using the stylistic plugin's quotes rule.

## Examples

Example of **incorrect** code:
```ts
const single = "single";
const double = 'double';
const mixed = "mixed' + 'quotes";

type Foo = {
  prop: "string";
};

interface Bar {
  method(): "return";
}
```

Example of **correct** code:
```ts
// Using single quotes
const single = 'single';
const double = 'double';
const template = `template`;

type Foo = {
  prop: 'string';
};

// Or using double quotes
const single = "single";
const double = "double";
const template = `template`;
```

See [eslint.style](https://eslint.style) for the current version of this rule.