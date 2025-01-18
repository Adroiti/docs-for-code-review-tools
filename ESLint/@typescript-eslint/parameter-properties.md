Pattern: Inconsistent constructor parameter property usage

Issue: -

## Description

TypeScript allows declaring class properties directly in constructor parameters using accessibility modifiers, but mixing this shorthand with regular property declarations can make code less consistent and harder to understand. A consistent approach should be used throughout the codebase.

## Examples

Example of **incorrect** code:
```ts
// Mixed usage of parameter properties and regular properties
class Person {
  private age: number;
  constructor(
    public name: string,  // Parameter property
    age: number          // Regular parameter
  ) {
    this.age = age;
  }
}

// Parameter property when prefer-class-property is set
class User {
  constructor(private readonly id: string) {}
}
```

Example of **correct** code:
```ts
// Consistent use of regular properties
class Person {
  private name: string;
  private age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

// Consistent use of parameter properties
class User {
  constructor(
    public name: string,
    public age: number
  ) {}
}
```