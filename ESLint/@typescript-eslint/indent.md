Pattern: Inconsistent code indentation

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent indentation levels in code, which can now be configured using the stylistic plugin's indent rule.

## Examples

Example of **incorrect** code:
```ts
function foo() {
   const x = 5;
  if (x) {
      return true;
}
}

type Person = {
  name: string,
    age: number
};
```

Example of **correct** code:
```ts
function foo() {
  const x = 5;
  if (x) {
    return true;
  }
}

type Person = {
  name: string,
  age: number
};
```

See [eslint.style](https://eslint.style) for the current version of this rule.