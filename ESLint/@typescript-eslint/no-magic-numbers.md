Pattern: Unnamed numeric constant

Issue: -

## Description

Magic numbers are numeric literals that appear in code without obvious meaning. They can harm code readability and maintainability since their purpose is unclear. Numbers should be assigned to constants with descriptive names to clarify their intent and ensure consistency.

## Examples

Example of **incorrect** code:
```ts
// Magic numbers in calculations
function getTotal(amount: number) {
  return amount * 1.0825;  // Tax rate
}

// Magic numbers in conditions
if (value > 86400) {
  // Do something
}

// Magic numbers in enum
enum Status {
  ERROR = 400,
  SUCCESS = 200
}

// Magic numbers in type literals
type Ports = 8080 | 3000;

// Magic numbers in array access
const item = items[1];

// Magic numbers in class properties
class Config {
  timeout = 5000;
  maxRetries = 3;
}
```

Example of **correct** code:
```ts
// Named constants
const TAX_RATE = 1.0825;
const SECONDS_IN_DAY = 86400;
const DEFAULT_TIMEOUT = 5000;

function getTotal(amount: number) {
  return amount * TAX_RATE;
}

// Enum with named constants
enum HttpStatus {
  ERROR = 400,
  SUCCESS = 200
}

// Named type literals
const enum Port {
  Dev = 3000,
  Test = 8080
}
type Ports = Port.Dev | Port.Test;

// Named indices
const FIRST_ITEM = 0;
const SECOND_ITEM = 1;
const item = items[SECOND_ITEM];

// Class with documented constants
class Config {
  static readonly DEFAULT_TIMEOUT = 5000;
  static readonly MAX_RETRIES = 3;
}
```