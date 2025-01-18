Pattern: Inconsistent generic type argument placement

Issue: -

## Description

When creating instances of generic classes, type arguments can be specified either on the type annotation (left-hand side) or the constructor call (right-hand side). Using both styles within the same codebase reduces readability and creates inconsistent patterns.

## Examples

Example of **incorrect** code when preferring constructor:
```ts
// Type arguments only on type annotation
const map: Map<string, number> = new Map();
const set: Set<string> = new Set();

const cache: Cache<string> = new Cache();
const list: List<number> = new List();
```

Example of **correct** code when preferring constructor:
```ts
// Type arguments on constructor
const map = new Map<string, number>();
const set = new Set<string>();

// Valid variations
const set = new Set(); // No type arguments needed
const map: CustomMap<string, number> = new MyMap(); // Different types
const set: Set<string> = new Set<string>(); // Both sides match
```

Example of **incorrect** code when preferring type annotation:
```ts
// Type arguments only on constructor
const map = new Map<string, number>();
const set = new Set<string>();

const cache = new Cache<string>();
```

Example of **correct** code when preferring type annotation:
```ts
// Type arguments on type annotation
const map: Map<string, number> = new Map();
const set: Set<string> = new Set();

// Valid variations
const set = new Set(); // No type arguments needed
const set: Set<string> = new Set<string>(); // Both sides match
```