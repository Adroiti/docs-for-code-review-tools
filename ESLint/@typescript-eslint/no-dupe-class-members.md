Pattern: Duplicate member declaration in class

Issue: -

## Description

Declaring the same class member multiple times can lead to unexpected behavior, as later declarations overwrite earlier ones. This applies to all members except method overloads, which TypeScript allows for type-safe polymorphic methods.

## Examples

Example of **incorrect** code:
```ts
class Example {
  foo = 1;
  foo = 2;  // Overwrites previous declaration

  bar() { return 1; }
  bar() { return 2; }  // Overwrites previous method

  get baz() { return 'a'; }
  get baz() { return 'b'; }  // Overwrites previous getter
}
```

Example of **correct** code:
```ts
class Example {
  // Single property declaration
  foo = 1;

  // Valid method overloads
  bar(x: string): string;
  bar(x: number): number;
  bar(x: string | number): string | number {
    return x;
  }

  // Single getter
  get baz() { return 'a'; }
}
```