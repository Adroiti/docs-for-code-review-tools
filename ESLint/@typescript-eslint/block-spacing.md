Pattern: Inconsistent spacing within blocks

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing within blocks (between curly braces), which can now be configured using the stylistic plugin's block-spacing rule.

## Examples

Example of **incorrect** code:
```ts
function foo() {return true;}

if (foo) { return bar;}

function baz() {let i = 0;}
```

Example of **correct** code:
```ts
function foo() { return true; }

if (foo) { return bar; }

function baz() { let i = 0; }
```

See [eslint.style](https://eslint.style) for the current version of this rule.