Pattern: Mixed indexed object type syntax

Issue: -

## Description

TypeScript provides multiple ways to define objects with arbitrary keys: index signatures (`[key: string]: T`), mapped types (`[K in string]: T`), and the `Record` utility type. Using different styles within the same codebase reduces readability and creates inconsistent patterns.

## Examples

Example of **incorrect** code when preferring Record:
```ts
// Using index signature
interface StringMap {
  [key: string]: unknown;
}

// Using type with index signature
type NumberMap = {
  [key: number]: string;
};

// Using mapped type
type BooleanMap = {
  [K in string]: boolean;
};
```

Example of **correct** code when preferring Record:
```ts
// Using Record consistently
type StringMap = Record<string, unknown>;
type NumberMap = Record<number, string>;
type BooleanMap = Record<string, boolean>;
```

Example of **incorrect** code when preferring index signature:
```ts
// Using Record type
type StringMap = Record<string, unknown>;
type NumberMap = Record<number, string>;
```

Example of **correct** code when preferring index signature:
```ts
// Using index signature consistently
interface StringMap {
  [key: string]: unknown;
}

type NumberMap = {
  [key: number]: string;
};

interface DataMap {
  [key: string]: number;
}
```