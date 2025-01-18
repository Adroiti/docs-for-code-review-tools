Pattern: Excessive parameter count in function

Issue: -

## Description

Functions with many parameters are difficult to read, maintain, and call correctly. When a function has too many parameters, it often indicates that it should be restructured, possibly by grouping related parameters into objects or breaking the function into smaller, more focused functions.

## Examples

Example of **incorrect** code with max 3 parameters:
```ts
// Too many parameters
function createUser(name: string, age: number, email: string, address: string) {
  // ...
}

// Arrow function with too many parameters
const processData = (id: number, data: string, type: string, validate: boolean) => {
  // ...
};

class Form {
  // Method with too many parameters
  submit(data: FormData, token: string, userId: string, timestamp: number) {
    // ...
  }
}
```

Example of **correct** code:
```ts
// Using an options object
interface UserOptions {
  name: string;
  age: number;
  email: string;
  address: string;
}

function createUser(options: UserOptions) {
  // ...
}

// Within parameter limit
function processItem(id: number, data: string, type: string) {
  // ...
}

// Using class structure to reduce parameters
class Form {
  private token: string;
  private userId: string;

  submit(data: FormData) {
    // ...
  }
}

// this parameter doesn't count when configured
function setup(this: void, a: string, b: string, c: string) {
  // ...
}
```