Pattern: Redundant enum or namespace qualifier

Issue: -

## Description

When accessing members within their parent enum or namespace, using the parent name as a qualifier is unnecessary. The members can be accessed directly by their name without the parent qualification.

## Examples

Example of **incorrect** code:
```ts
enum A {
  B,
  C = A.B,
}

namespace A {
  export type B = number;
  const x: A.B = 3;
}
```

Example of **correct** code:
```ts
enum A {
  B,
  C = B,
}

namespace A {
  export type B = number;
  const x: B = 3;
}
```