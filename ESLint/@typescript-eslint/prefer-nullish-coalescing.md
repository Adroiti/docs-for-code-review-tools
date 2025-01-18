Pattern: Logical OR over nullish coalescing

Issue: -

## Description

Using the logical OR operator (`||`) to provide default values can lead to unexpected behavior because it triggers on any falsy value (`''`, `0`, `false`, etc). The nullish coalescing operator (`??`) only provides the fallback for `null` or `undefined`, making it safer and more predictable.

## Examples

Example of **incorrect** code:
```ts
// Using || which triggers on any falsy value
let value = foo || 'default';
foo ||= 'default';

function example(foo?: string) {
  return foo || 'default';
}

const title = user.title || 'Untitled';
const id = obj.id || generateId();
```

Example of **correct** code:
```ts
// Using ?? which only triggers on null or undefined
let value = foo ?? 'default';
foo ??= 'default';

function example(foo?: string) {
  return foo ?? 'default';
}

const title = user.title ?? 'Untitled';
const id = obj.id ?? generateId();

// Using || is fine when falsy coalescing is intended
const isEnabled = flag || false;
const count = getCount() || 0;
```