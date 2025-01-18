Pattern: Inconsistent semicolon usage

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent use of semicolons at the end of statements, which can now be configured using the stylistic plugin's semi rule.

## Examples

Example of **incorrect** code:
```ts
// Missing semicolons
const a = 1
let b = 2

// With semicolons when configured to omit them
const c = 3;
let d = 4;

// Interface and type members
interface Foo {
  prop: string
  method(): void
}

type Bar = {
  prop: string
  method(): void
}
```

Example of **correct** code:
```ts
// With semicolons
const a = 1;
let b = 2;

interface Foo {
  prop: string;
  method(): void;
}

// Or without semicolons
const a = 1
let b = 2

interface Foo {
  prop: string
  method(): void
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.