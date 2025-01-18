Pattern: Missing spaces around infix operators

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent spacing around infix operators (including type operators), which can now be configured using the stylistic plugin's space-infix-ops rule.

## Examples

Example of **incorrect** code:
```ts
// Arithmetic operators
let sum = 1+2;
let product = value*2;

// Assignment operators
let x=1;
let y+=2;

// Type operators
type T = string&number;
type U = 'a'|'b';

// Comparison and logical
if (foo&&bar||baz) {}

// Type parameters
type Container<T=string> = T[];
function transform<T=object,U=unknown>(value: T): U {}
```

Example of **correct** code:
```ts
// Arithmetic operators
let sum = 1 + 2;
let product = value * 2;

// Assignment operators
let x = 1;
let y += 2;

// Type operators
type T = string & number;
type U = 'a' | 'b';

// Comparison and logical
if (foo && bar || baz) {}

// Type parameters
type Container<T = string> = T[];
function transform<T = object, U = unknown>(value: T): U {}
```

See [eslint.style](https://eslint.style) for the current version of this rule.