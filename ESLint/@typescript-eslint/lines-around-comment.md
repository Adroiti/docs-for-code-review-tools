Pattern: Missing empty lines around comments

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent empty lines before and after comments, which can now be configured using the stylistic plugin's lines-around-comment rule.

## Examples

Example of **incorrect** code:
```ts
const a = 1;
// This is a comment
const b = 2;
/* This is another comment */
const c = 3;
/** This is a doc comment */
function foo() {}
```

Example of **correct** code:
```ts
const a = 1;

// This is a comment
const b = 2;

/* This is another comment */
const c = 3;

/** This is a doc comment */
function foo() {}
```

See [eslint.style](https://eslint.style) for the current version of this rule.