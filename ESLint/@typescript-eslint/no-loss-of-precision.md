Pattern: Numeric literal with precision loss

Issue: -

## Description

⚠️ This rule is deprecated. Use `eslint/no-loss-of-precision` instead.

Numbers in JavaScript that exceed certain lengths can lose precision when represented in the language. This can lead to unexpected behavior and bugs in calculations. Using such numbers directly as literals should be avoided.

## Examples

Example of **incorrect** code:
```ts
const x = 9007199254740993; // 2^53 + 1
const y = 5123000000000000000000000000001;
const z = 1.0000000000000001;
```

Example of **correct** code:
```ts
const x = 9007199254740991; // 2^53 - 1
const y = 1.0;
const z = 123456789;

// Using numeric separators for clarity
const budget = 1_000_000_000;
const binary = 0b1010_0001;
const hex = 0xFF_FF_FF_FF;
```