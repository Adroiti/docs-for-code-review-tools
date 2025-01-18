Pattern: Interface with single call signature

Issue: -

## Description

Using interfaces or object type literals with a single call signature is more verbose than using equivalent function types. When a type only defines how something can be called, the function type syntax (`() => type`) is clearer and more concise than an interface or object type with a call signature.

## Examples

Example of **incorrect** code:
```ts
interface Example {
  (): string;
}

function foo(example: { (): number }): number {
  return example();
}

interface ReturnsSelf {
  // returns the function itself
  (arg: string): this;
}
```

Example of **correct** code:
```ts
type Example = () => string;

function foo(example: () => number): number {
  return bar();
}

type ReturnsSelf = (arg: string) => ReturnsSelf;

// Multiple call signatures are fine
interface Overloaded {
  (data: string): number;
  (id: number): string;
}

// Interface with additional properties is fine
interface WithProperties {
  (): void;
  prop: string;
}
```