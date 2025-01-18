Pattern: Inconsistent spacing in function calls

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing between function name and the opening parenthesis in function calls, which can now be configured using the stylistic plugin's func-call-spacing rule.

## Examples

Example of **incorrect** code:
```ts
fn ();
fn
();
type T = Array <string>;
class X {
  constructor () {}
}
interface Y {
  method (): void;
}
```

Example of **correct** code:
```ts
fn();
type T = Array<string>;
class X {
  constructor() {}
}
interface Y {
  method(): void;
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.