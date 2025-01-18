Pattern: Mutable parameter type

Issue: -

## Description

Function parameters that can be mutated inside the function can lead to confusing behavior and make code harder to debug. Using readonly types for parameters provides a clear contract to consumers that the function will not modify its inputs, making code easier to reason about.

## Examples

Example of **incorrect** code:
```ts
function array1(arg: string[]) {}
function array2(arg: readonly string[][]) {}
function array3(arg: [string, number]) {}
function array4(arg: readonly [string[], number]) {}

function object1(arg: { prop: string }) {}
function object2(arg: { readonly prop: string; prop2: string }) {}
function object3(arg: { readonly prop: { prop2: string } }) {}

interface CustomArrayType extends ReadonlyArray<string> {
  prop: string;  // mutable property
}
function custom1(arg: CustomArrayType) {}
```

Example of **correct** code:
```ts
function array1(arg: readonly string[]) {}
function array2(arg: readonly (readonly string[])[]) {}
function array3(arg: readonly [string, number]) {}
function array4(arg: readonly [readonly string[], number]) {}

function object1(arg: { readonly prop: string }) {}
function object2(arg: { readonly prop: string; readonly prop2: string }) {}
function object3(arg: { readonly prop: { readonly prop2: string } }) {}

function primitive1(arg: string) {}
function primitive2(arg: number) {}
function primitive3(arg: boolean) {}

function fnSig(arg: () => void) {}
```