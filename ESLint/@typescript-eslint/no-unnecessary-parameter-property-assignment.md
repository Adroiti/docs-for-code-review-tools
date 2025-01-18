Pattern: Redundant parameter property assignment

Issue: -

## Description

When using TypeScript parameter properties (properties declared directly in constructor parameters), it's redundant to reassign the same value to the property inside the constructor. The parameter property declaration already handles the initialization, making the additional assignment unnecessary.

## Examples

Example of **incorrect** code:
```ts
class Example {
  constructor(
    private readonly name: string,
    public age: number,
    protected readonly id: string
  ) {
    // Redundant assignments
    this.name = name;
    this.age = age;
    this.id = id;
  }
}

class User {
  constructor(public email: string) {
    // Unnecessary reassignment
    this.email = email;
  }

  constructor(private readonly data: UserData) {
    // Redundant assignment of parameter property
    this.data = data;
  }
}
```

Example of **correct** code:
```ts
class Example {
  constructor(
    private readonly name: string,
    public age: number,
    protected readonly id: string
  ) {
    // No redundant assignments
  }
}

class User {
  constructor(public email: string) {
    // No unnecessary reassignment
  }
}

// When assignment is actually needed
class CustomUser {
  private readonly email: string;
  
  constructor(email: string) {
    // Not a parameter property, assignment is necessary
    this.email = email.toLowerCase();
  }
}

class DataProcessor {
  constructor(private readonly data: UserData) {
    // Additional logic without reassignment
    this.processData();
  }
}
```