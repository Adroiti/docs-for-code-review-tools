Pattern: Logical AND chaining instead of optional chain

Issue: -

## Description

Using logical AND (`&&`) operators for null checks is less safe than using optional chaining (`?.`). The `&&` operator chains on any falsy value, while `?.` only chains on `null` or `undefined`. This makes `?.` more predictable and often results in more concise code.

## Examples

Example of **incorrect** code:
```ts
foo && foo.a && foo.a.b && foo.a.b.c;
foo && foo['a'] && foo['a'].b && foo['a'].b.c;
foo && foo.a && foo.a.b && foo.a.b.method && foo.a.b.method();

// With empty objects
(((foo || {}).a || {}).b || {}).c;

// With negated or's
!foo || !foo.bar;
!foo || !foo[bar];
!foo || !foo.bar || !foo.bar.baz();

// With nullish checks
foo && foo.a != null && foo.a.b !== null && foo.a.b.c;
```

Example of **correct** code:
```ts
foo?.a?.b?.c;
foo?.['a']?.b?.c;
foo?.a?.b?.method?.();

foo?.a?.b?.c?.d?.e;

!foo?.bar;
!foo?.[bar];
!foo?.bar?.baz?.();
```