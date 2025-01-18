Pattern: Missing padding line between statements

Issue: -

## Description

This rule has been moved to the ESLint stylistic plugin. It enforced consistent empty lines between different types of statements, which can now be configured using the stylistic plugin's padding-line-between-statements rule.

## Examples

Example of **incorrect** code:
```ts
import { foo } from 'foo';
const bar = 1;
function baz() {
  return true;
}
export { baz };

function qux() {
  const x = 1;
  return x;
}
```

Example of **correct** code:
```ts
import { foo } from 'foo';

const bar = 1;

function baz() {
  return true;
}

export { baz };

function qux() {
  const x = 1;

  return x;
}
```

See [eslint.style](https://eslint.style) for the current version of this rule.