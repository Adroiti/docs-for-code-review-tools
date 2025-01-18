Pattern: Missing space before block

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing before blocks (curly braces), which can now be configured using the stylistic plugin's space-before-blocks rule.

## Examples

Example of **incorrect** code:
```ts
if (foo){
  bar();
}

function foo(){
  bar();
}

class Foo{
  constructor(){
    bar();
  }
}

interface Bar{
  method(): void;
}
```

Example of **correct** code:
```ts
if (foo) {
  bar();
}

function foo() {
  bar();
}

class Foo {
  constructor() {
    bar();
  }
}

interface Bar {
  method(): void;
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.