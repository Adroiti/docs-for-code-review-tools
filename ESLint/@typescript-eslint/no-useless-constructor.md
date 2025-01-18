Pattern: Constructor that adds no value

Issue: -

## Description

Constructors that only call the parent constructor with the same arguments or have no implementation are unnecessary and can be omitted. This includes constructors marked as `protected`/`private`, `public` constructors with no superclass, and constructors with only parameter properties.

## Examples

Example of **incorrect** code:
```ts
class A {
  constructor() {
  }
}

class B extends A {
  constructor(x: number) {
    super(x);
  }
}

class C {
  constructor(public x: number) {}
}
```

Example of **correct** code:
```ts
class A {
  // No constructor needed
}

class B extends A {
  // No constructor needed when just forwarding arguments
}

class C {
  constructor(public x: number, protected y: string) {
    // Constructor needed when doing more than just property assignment
    console.log('Initializing...');
  }
}
```