Pattern: Class method without this reference

Issue: -

## Description

A class method that doesn't use this could be made into a static method or standalone function. Instance methods that don't use this often indicate a design issue, as they don't interact with the instance's state. This rule has exceptions for override methods and interface implementations.

## Examples

Example of **incorrect** code:
```ts
class Calculator {
  // Method doesn't use this
  add(a: number, b: number) {
    return a + b;
  }

  // Arrow function property doesn't use this
  multiply = (a: number, b: number) => {
    return a * b;
  };

  // Private method doesn't use this
  private validateInput(value: number) {
    return value > 0;
  }
}

class StringBuilder {
  // Multiple methods not using this
  capitalize(str: string) {
    return str.toUpperCase();
  }
  
  lowercase(str: string) {
    return str.toLowerCase();
  }
}
```

Example of **correct** code:
```ts
class Calculator {
  private value: number;

  // Method uses this
  add(a: number) {
    this.value += a;
    return this.value;
  }

  // Static method for utility function
  static multiply(a: number, b: number) {
    return a * b;
  }

  // Override method allowed when configured
  override validate() {
    return true;
  }
}

// Interface implementation allowed when configured
class Handler implements IHandler {
  handle(event: Event) {
    console.log(event);
  }
}
```