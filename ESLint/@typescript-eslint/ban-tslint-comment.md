Pattern: Lingering TSLint directive comment

Issue: -

## Description

TSLint comment directives should be removed after migrating to ESLint. These comments no longer serve any purpose and can create confusion. Any necessary rule suppression should be done using ESLint's own comment directives.

## Examples

Example of **incorrect** code:
```ts
/* tslint:disable */
const x = 5;

// tslint:disable-next-line
function example() {}

someCode(); // tslint:disable-line

/* tslint:disable:rule1 rule2 rule3 */
const y = 10;

// tslint:disable-next-line:rule1 rule2
const z = 15;
```

Example of **correct** code:
```ts
/* eslint-disable */
const x = 5;

// eslint-disable-next-line
function example() {}

// Regular comments that mention tslint are fine
// Note: This was previously checked by tslint
const y = 10;

/* Just mentioning tslint in a comment is fine */
const z = 15;
```