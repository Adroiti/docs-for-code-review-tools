Pattern: Mixed value types in enum members

Issue: -

## Description

Mixing numeric and string values in a single enum creates confusing behavior, especially when iterating over enum values. With mixed enums, iteration methods like Object.values() will include both the numeric keys and values, leading to unexpected results.

## Examples

Example of **incorrect** code:
```ts
// Mixed number and string values
enum Status {
  Active = 0,
  Pending = 'PENDING',
  Done = 1
}

// Implicit numbers with string
enum Result {
  Success,
  Error = 'ERROR',
  Unknown
}

// Computed values mixing types
enum Operation {
  Read = 1,
  Write = 1 << 1,
  Execute = 'EXECUTE'
}

// Mixed types with aliases
enum Permission {
  None = 0,
  Basic = None,
  Admin = 'ADMIN'
}
```

Example of **correct** code:
```ts
// All numeric enum
enum Status {
  Active = 0,
  Pending = 1,
  Done = 2
}

// All string enum
enum Result {
  Success = 'SUCCESS',
  Error = 'ERROR',
  Unknown = 'UNKNOWN'
}

// Numeric enum with computations
enum Permission {
  None = 0,
  Read = 1 << 0,
  Write = 1 << 1,
  Execute = 1 << 2
}

// String enum with consistent values
enum Operation {
  Read = 'READ',
  Write = 'WRITE',
  Execute = 'EXECUTE'
}

// Using separate enums for different types
enum NumericStates {
  Active = 1,
  Inactive = 0
}

enum StringStates {
  Active = 'ACTIVE',
  Inactive = 'INACTIVE'
}
```