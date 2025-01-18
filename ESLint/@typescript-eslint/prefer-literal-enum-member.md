Pattern: Non-literal enum value

Issue: -

## Description

Using non-literal values in enum members can lead to unexpected results due to TypeScript's enum scoping rules. When an enum member references variables or expressions, the resulting values can be confusing and may not match developer expectations. Literal values provide clearer, more predictable enum definitions.

## Examples

Example of **incorrect** code:
```ts
const str = 'Test';
const string1 = 'string1';
const string2 = 'string2';

enum Invalid {
  A = str,                   // Variable assignment
  B = `Interpolates ${string1} and ${string2}`,  // Template literal with interpolation
  C = 2 + 2,                // Expression assignment
  D = C,                    // Assignment to another enum member
}
```

Example of **correct** code:
```ts
enum Valid {
  A,                              // No initializer
  B = 'TestStr',                  // String literal
  C = `A template literal string`, // Template literal without interpolation
  D = 4,                          // Number literal
}
```