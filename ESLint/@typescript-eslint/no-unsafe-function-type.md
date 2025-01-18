Pattern: Use of built-in Function type

Issue: -

## Description

The built-in `Function` type is unsafe as it allows calls with any arguments and returns `any`. It also permits assignment of classes or objects that have Function properties. Using explicit function types with defined parameters and return types provides better type safety.

## Examples

Example of **incorrect** code:
```ts
let noParametersOrReturn: Function;
noParametersOrReturn = () => {};

let stringToNumber: Function;
stringToNumber = (text: string) => text.length;

let identity: Function;
identity = value => value;
```

Example of **correct** code:
```ts
let noParametersOrReturn: () => void;
noParametersOrReturn = () => {};

let stringToNumber: (text: string) => number;
stringToNumber = text => text.length;

let identity: <T>(value: T) => T;
identity = value => value;
```