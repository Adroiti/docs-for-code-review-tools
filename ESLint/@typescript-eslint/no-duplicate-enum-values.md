Pattern: Duplicate value in enum member

Issue: -

## Description

While TypeScript allows multiple enum members to share the same value, this often indicates a mistake and can lead to confusing behavior. Each enum member should have a unique value to maintain clear mappings between names and values.

## Examples

Example of **incorrect** code:
```ts
enum Status {
  Active = 1,
  Running = 1,  // Same as Active
}

enum Direction {
  Up = 'NORTH',
  North = 'NORTH',  // Same as Up
}

enum ResultCode {
  Success = 200,
  OK = 200,  // Same as Success
  Error = Success,  // Implicitly same value
}
```

Example of **correct** code:
```ts
enum Status {
  Active = 1,
  Running = 2,
}

enum Direction {
  Up = 'UP',
  North = 'NORTH',
}

enum ResultCode {
  Success = 200,
  Created = 201,
  // Using computed values is fine
  ServerError = computeValue(),
  // Using indirection is fine
  ClientError = ServerError + 100,
}
```