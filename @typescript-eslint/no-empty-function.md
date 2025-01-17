Pattern: Empty function body without explanation

Issue: -

## Description

Empty functions can indicate incomplete implementation or unnecessary code. While there are valid cases for empty functions (like interface implementation stubs or overrides), unexplained empty functions often indicate a mistake or missing implementation.

## Examples

Example of **incorrect** code:
```ts
// Empty functions without purpose
function doNothing() {}

const noop = () => {};

class Example {
  method() {}
  
  get value() {}
  
  set value(v) {}
}

// Empty event handlers
element.onclick = function() {};
button.addEventListener('click', () => {});
```

Example of **correct** code:
```ts
// Protected/private constructors can be empty
class Utility {
  private constructor() {}
}

// Empty override is valid when configured
class Child extends Parent {
  override method() {}
}

// Decorated empty methods are valid when configured
class API {
  @LogAccess()
  openConnection() {}
}

// Explicit interface implementation
class Handler implements IHandler {
  handle(): void {}
}

// Using proper stubs/mocks in tests
const mockFunction = jest.fn();
const spy = sinon.spy();

// Empty handlers with comments explaining purpose
function noop() {
  // Used as default callback
}
```