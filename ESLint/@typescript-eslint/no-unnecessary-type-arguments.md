Pattern: Redundant type argument matching default

Issue: -

## Description

When a type parameter has a default value, explicitly providing that same type as an argument is redundant and adds unnecessary verbosity to the code. The default type will be used automatically if no type argument is provided.

## Examples

Example of **incorrect** code:
```ts
function f<T = number>() {}
f<number>();

function g<T = number, U = string>() {}
g<string, string>();

class C<T = number> {}
new C<number>();
class D extends C<number> {}

interface I<T = number> {}
class Impl implements I<number> {}
```

Example of **correct** code:
```ts
function f<T = number>() {}
f();
f<string>();

function g<T = number, U = string>() {}
g<string>();
g<number, number>();

class C<T = number> {}
new C();
new C<string>();
class D extends C {};
class D extends C<string> {};

interface I<T = number> {}
class Impl implements I<string> {}
```