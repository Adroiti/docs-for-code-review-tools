Pattern: Non-null assertion after optional chain

Issue: -

## Description

Using a non-null assertion (!) after an optional chain (?.) is contradictory since optional chaining is specifically designed to handle null/undefined cases by returning undefined. This combination indicates either an unnecessary optional chain or an incorrect non-null assertion.

## Examples

Example of **incorrect** code:
```ts
// Non-null assertion after optional property access
object?.property!;

// Non-null assertion after optional method call
object?.method()!;

// Chained non-null assertions
object?.prop1?.prop2!.prop3!;

// Non-null assertion after nested optional chain
obj?.nested?.value!;

// Non-null assertion with method result
async function example() {
  return (await foo?.bar())!;
}
```

Example of **correct** code:
```ts
// Optional chain without assertion
object?.property;

// Optional method call without assertion
object?.method();

// Proper null checking with optional chain
const value = object?.property ?? defaultValue;

// Type guard for non-null values
if (object?.property != null) {
  useProperty(object.property);
}

// Early return for null cases
const value = object?.property;
if (value === undefined) return;

// Proper nullish coalescing
const result = obj?.nested?.value ?? defaultValue;
```