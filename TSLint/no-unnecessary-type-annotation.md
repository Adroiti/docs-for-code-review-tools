Pattern: Unnecessary type annotation

Issue: -

## Description

Finds type annotations of variables and parameters that can be removed because the compiler can infer the type.

**Known limitation:** sometimes removing a type annotation can cause circular inference and therefore a compiler error.

## Examples

```ts
const foo: 1 = 1;
const foo: number = 1;
let foo: number = 1;
const arr: string[] = ["foo", "bar"];

const myVerboseSignature: (a: number) => number = function(a: number): number {
    return a;
}

declare function takeCallback(cb: (a: string) => void): void;
takeCallback((a: string) => a);
```

## Options

#### `"check-return-type"`

Enables checking function return types. This option can cause false positives for (mutually) recursive functions.

## Further Reading

* [TSLint - no-unnecessary-type-annotation](https://github.com/ajafff/tslint-consistent-codestyle/blob/master/docs/no-unnecessary-type-annotation.md)