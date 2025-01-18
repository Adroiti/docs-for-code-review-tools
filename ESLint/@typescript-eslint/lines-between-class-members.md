Pattern: Missing empty lines between class members

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent empty lines between class members, which can now be configured using the stylistic plugin's lines-between-class-members rule.

## Examples

Example of **incorrect** code:
```ts
class MyClass {
  foo(): void {}
  bar(): void {}
  baz: string;
  qux(): number {
    return 1;
  }
}
```

Example of **correct** code:
```ts
class MyClass {
  foo(): void {}

  bar(): void {}

  baz: string;

  qux(): number {
    return 1;
  }
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.