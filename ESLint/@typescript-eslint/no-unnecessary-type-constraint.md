Pattern: Redundant type parameter constraint

Issue: -

## Description

Generic type parameters default to an implicit `extends unknown` constraint. Explicitly extending from `any` or `unknown` is therefore redundant and adds unnecessary verbosity to the code.

## Examples

Example of **incorrect** code:
```ts
interface FooAny<T extends any> {}

interface FooUnknown<T extends unknown> {}

type BarAny<T extends any> = {};

type BarUnknown<T extends unknown> = {};

class BazAny<T extends any> {
  quxAny<U extends any>() {}
}

const QuuxAny = <T extends any>() => {};

function QuuzAny<T extends any>() {}
```

Example of **correct** code:
```ts
interface Foo<T> {}

type Bar<T> = {};

class Baz<T> {
  qux<U>() {}
}

const Quux = <T>() => {};

function Quuz<T>() {}
```