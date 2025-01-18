Pattern: Type alias instead of interface

Issue: -

## Description

Type aliases can sometimes be replaced with interfaces, which provide better code reuse through extension and implementation. While type aliases are useful for complex types, unions, and intersections, using them for simple object types can limit maintainability and debugging capabilities.

## Examples

Example of **incorrect** code:
```ts
type Person = {
  name: string;
  age: number;
};

type StringAlias = string;

type UserCallback = () => void;

type Size = 'small' | 'medium' | 'large';
```

Example of **correct** code:
```ts
interface Person {
  name: string;
  age: number;
}

// For unions and complex types, type aliases are acceptable
type Theme = 'light' | 'dark';
type Callback<T> = (data: T) => void;
type Immutable<T> = { readonly [P in keyof T]: T[P] };
```