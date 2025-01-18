Pattern: Unordered type union/intersection member

Issue: -

## Description

Having type unions (`|`) and intersections (`&`) in an inconsistent order makes it harder to scan code quickly, find duplicates, and maintain consistency across a codebase. The types should be sorted alphabetically (case-insensitive) with numbers sorted naturally.

## Examples

Example of **incorrect** code:
```ts
// Unsorted unions
type T1 = B | A;
type T2 = 'zebra' | 'apple' | 'banana';
type T3 = number[] | string | number | string[];

// Unsorted intersections
type T4 = { b: string } & { a: string };
type T5 = [1, 2, 4] & [1, 2, 3];

// Mixed unordered types
type T6 = [1, 2, 4] | { b: string } | 'b' | 'a' | B | A | string;
```

Example of **correct** code:
```ts
// Sorted unions
type T1 = A | B;
type T2 = 'apple' | 'banana' | 'zebra';
type T3 = number | number[] | string | string[];

// Sorted intersections
type T4 = { a: string } & { b: string };
type T5 = [1, 2, 3] & [1, 2, 4];

// Mixed ordered types
type T6 = A | B | 'a' | 'b' | string | { b: string } | [1, 2, 4];
```