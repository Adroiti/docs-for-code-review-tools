Pattern: Optional parameter before required parameter

Issue: -

## Description

Function parameters with default values or optional markers (?) should appear after required parameters. Having optional parameters before required ones creates confusing function signatures and makes it harder to understand which arguments correspond to which parameters.

## Examples

Example of **incorrect** code:
```ts
// Default parameter before required
function process(name = 'default', id: string) {}

// Optional parameter before required
function query(filter?: string, limit: number) {}

// Mixed in class constructor
class User {
  constructor(
    private name = 'anonymous',
    private id: string,
  ) {}
}

// Optional before required in method
class API {
  fetch(cache?: boolean, endpoint: string) {}
}
```

Example of **correct** code:
```ts
// Required parameters before default
function process(id: string, name = 'default') {}

// Required before optional
function query(limit: number, filter?: string) {}

// Properly ordered class constructor
class User {
  constructor(
    private id: string,
    private name = 'anonymous',
  ) {}
}

// Multiple optional parameters at end
function configure(
  required: string,
  optional1?: string,
  optional2?: number,
) {}

// All optional parameters
function init(config?: Config, options?: Options) {}
```