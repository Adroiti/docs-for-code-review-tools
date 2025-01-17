Pattern: Constructor/new method misuse

Issue: -

## Description

Misusing constructor and new keywords in classes and interfaces can lead to confusing and incorrect code. Classes should use constructor methods for initialization, while interfaces describing class types should use new() signatures. Using them incorrectly (new in a class or constructor in an interface) indicates a misunderstanding of their purpose.

## Examples

Example of **incorrect** code:
```ts
// Class with 'new' method instead of constructor
class User {
  new(): User {
    return new User();
  }
}

// Interface with constructor method
interface UserFactory {
  constructor(): void;
}

// Interface with mixed constructor and new
interface Factory {
  new(): Factory;
  constructor(): void;
}

// Class extending interface with constructor
interface Base {
  constructor(): void;
}
class Derived implements Base {
  constructor() {}
}
```

Example of **correct** code:
```ts
// Class with proper constructor
class User {
  constructor() {
    // initialization
  }
}

// Interface describing class constructor
interface UserFactory {
  new(): User;
}

// Static factory method in class
class Factory {
  static create(): Factory {
    return new Factory();
  }
}

// Interface with proper new signature
interface Constructor {
  new(): object;
}

// Proper factory interface implementation
interface Factory<T> {
  new(): T;
}
class StringFactory implements Factory<string> {
  constructor() {}
}
```