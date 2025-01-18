Pattern: Duplicate type constituent in union or intersection

Issue: -

## Description

A redundant type constituent in a union or intersection type makes code unnecessarily verbose and can mask programmer errors. This includes duplicate literal types, duplicate interface members, and unnecessary undefined in optional parameters. Such duplicates should be removed to improve code clarity.

## Examples

Example of **incorrect** code:
```ts
// Duplicate literal types
type Status = 'active' | 'inactive' | 'active';

// Duplicate member types
type User = {name: string} & {name: string};

// Redundant undefined in optional parameter
function greet(name?: string | undefined) {}

// Duplicate type references
type StringA = string;
type StringB = string;
type Names = StringA | StringB;

// Same array type duplicated
type Numbers = [1, 2, 3] | [1, 2, 3];
```

Example of **correct** code:
```ts
// No duplicate types
type Status = 'active' | 'inactive';

// Different member types
type User = {name: string} & {age: number};

// Optional parameter without redundant undefined
function greet(name?: string) {}

// Different type references
type StringType = string;
type NumberType = number;
type Data = StringType | NumberType;

// Different array types
type Numbers = [1, 2, 3] | [1, 2, 3, 4];
```