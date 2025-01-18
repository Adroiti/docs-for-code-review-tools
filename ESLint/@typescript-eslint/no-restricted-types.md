Pattern: Usage of restricted type

Issue: -

## Description

Certain types may be deprecated, unsafe, or disallowed in a codebase. Using these types in annotations can perpetuate technical debt or introduce type safety issues. The rule helps enforce migration from old types to new ones and prevents usage of problematic types.

## Examples

Example of **incorrect** code:
```ts
// Using deprecated type
type UserData = OldUserType;

// Using unsafe type
function process(data: UnsafeType) {}

// Generic usage of banned type
type Container<T> = OldWrapper<T>;

// Extending restricted interface
interface NewThing extends OldThing {}

// Union with banned type
type Status = NewStatus | DeprecatedStatus;

// Return type annotation
function getData(): LegacyResponse {}

// Parameter type annotation
function update(config: OldConfig) {}
```

Example of **correct** code:
```ts
// Using replacement type
type UserData = NewUserType;

// Using safe alternative
function process(data: SafeType) {}

// Modern generic usage
type Container<T> = NewWrapper<T>;

// Using current interface
interface NewThing extends CurrentThing {}

// Clean union type
type Status = NewStatus;

// Updated return type
function getData(): CurrentResponse {}

// Modern parameter type
function update(config: CurrentConfig) {}

// Using suggested alternatives
type Config = RecommendedConfig;
```