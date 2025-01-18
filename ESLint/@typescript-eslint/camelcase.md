Pattern: Non-camelcase identifier

Issue: -

## Description

This rule has been deprecated in favor of the more comprehensive `naming-convention` rule. The camelcase rule enforced camelCase naming convention, but the naming-convention rule provides more granular control over naming patterns for different types of identifiers.

## Examples

Example of **incorrect** code:
```ts
const my_variable = 'value';
function do_something() { }
interface Some_Interface { }
class some_class { }
const MY_CONSTANT = 'value';
```

Example of **correct** code:
```ts
const myVariable = 'value';
function doSomething() { }
interface SomeInterface { }
class SomeClass { }
const MY_CONSTANT = 'value'; // Constants can use UPPER_SNAKE_CASE

// With naming-convention rule you can configure different styles
// for different types of identifiers
```

See the [naming-convention](./naming-convention.md) rule for the current replacement.