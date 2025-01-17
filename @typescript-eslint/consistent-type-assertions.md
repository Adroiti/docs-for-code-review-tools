Pattern: Mixed type assertion syntax

Issue: -

## Description

TypeScript allows two different type assertion syntaxes (`<Type>value` and `value as Type`). Using both styles in the same codebase reduces readability and can cause confusion, especially when angle-bracket assertions conflict with JSX syntax.

## Examples

Example of **incorrect** code:
```ts
// Mixed assertion styles
const a = <string>rawValue;
const b = otherValue as number;

// Object literal assertions that may hide errors
const obj = {} as ComplexType;
const arr = [] as string[];

// Assertions that could be type annotations
const x = { prop: 'value' } as Props;
const nums = [1, 2, 3] as number[];
```

Example of **correct** code:
```ts
// Consistent 'as' style assertions
const a = rawValue as string;
const b = otherValue as number;

// Type annotations instead of assertions
const obj: ComplexType = { field: 'value' };
const arr: string[] = [];

// Valid use of assertions
const constValue = { prop: 'value' } as const;
const unknownValue = value as unknown as SpecificType;

// Assertions in component props
const element = <Component prop={value as PropType} />;

// Assertions to any/unknown are allowed
const difficult = value as any;
const safer = value as unknown;
```