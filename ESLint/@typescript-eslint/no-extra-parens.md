Pattern: Unnecessary parentheses

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced removal of unnecessary parentheses that don't affect operation precedence, which can now be configured using the stylistic plugin's no-extra-parens rule.

## Examples

Example of **incorrect** code:
```ts
// Expression statements
const a = (4);
const b = ((1 + 2));

// Type assertions
const c = (<number>(5));
const d = (x as string);

// Return statements
function foo() {
  return (1 + 2);
}

// Arrow functions
const bar = (x) => (x + 1);
```

Example of **correct** code:
```ts
const a = 4;
const b = 1 + 2;

const c = <number>5;
const d = x as string;

function foo() {
  return 1 + 2;
}

const bar = x => x + 1;

// Necessary for precedence
const e = (a + b) * c;
```

See [eslint.style](https://eslint.style) for the current version of this rule.