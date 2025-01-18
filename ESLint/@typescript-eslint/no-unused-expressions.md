Pattern: Expression without side effects

Issue: -

## Description

Expressions that do nothing but state a type or value without creating side effects are redundant and can confuse readers. This includes standalone type assertions, instantiation expressions without assignment, and type assertions that don't change runtime behavior.

## Examples

Example of **incorrect** code:
```ts
Set<number>;
1 as number;
window!;
```

Example of **correct** code:
```ts
function getSet() {
  return Set;
}

// Function calls are allowed, so type expressions that wrap function calls are allowed
getSet()<number>;
getSet() as Set<unknown>;
getSet()!;

// Namespaces can have directives
namespace A {
  'use strict';
}
```