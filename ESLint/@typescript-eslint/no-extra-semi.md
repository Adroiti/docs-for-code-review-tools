Pattern: Unnecessary semicolon

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It prevented unnecessary semicolons that don't contribute to statement termination, which can now be configured using the stylistic plugin's no-extra-semi rule.

## Examples

Example of **incorrect** code:
```ts
const x = 5;;

class C {
  field = 1;;;

  method() {;};;

};

interface I {
  prop: string;;
  method(): void;;
}
```

Example of **correct** code:
```ts
const x = 5;

class C {
  field = 1;

  method() {}
}

interface I {
  prop: string;
  method(): void;
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.