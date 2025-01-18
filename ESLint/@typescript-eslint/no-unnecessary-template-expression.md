Pattern: Redundant template literal expression

Issue: -

## Description

Template literals that contain substitution expressions that can be simplified into regular strings or direct variable references create unnecessary complexity. This includes static values that can be incorporated into the template string directly, or expressions that are already strings.

## Examples

Example of **incorrect** code:
```ts
// Static values that could be in the template directly
const ab1 = `${'a'}${'b'}`;
const ab2 = `a${'b'}`;
const stringWithNumber = `${'1 + 1 = '}${2}`;
const stringWithBoolean = `${'true is '}${true}`;

// Simple expressions that are already strings
const text = 'a';
const wrappedText = `${text}`;

declare const intersectionWithString: string & { _brand: 'test-brand' };
const wrappedIntersection = `${intersectionWithString}`;
```

Example of **correct** code:
```ts
// Static values incorporated directly
const ab1 = `ab`;
const ab2 = `ab`;
const stringWithNumber = `1 + 1 = 2`;
const stringWithBoolean = `true is true`;

// Direct string references
const text = 'a';
const wrappedText = text;

declare const intersectionWithString: string & { _brand: 'test-brand' };
const wrappedIntersection = intersectionWithString;
```