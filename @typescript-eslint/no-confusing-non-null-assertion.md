Pattern: Ambiguous non-null assertion in comparison

Issue: -

## Description

A non-null assertion (`!`) placed immediately next to a comparison operator (`==`, `===`, `in`, `instanceof`) creates visually ambiguous code that can be mistaken for inequality checks (`!=`, `!==`) or negated tests (`!(a instanceof b)`). These assertions should be wrapped in parentheses or moved to avoid confusion.

## Examples

Example of **incorrect** code:
```ts
// Can be mistaken for inequality
foo.bar! == baz;
foo.bar! === baz;

// Can be mistaken for negation
foo! instanceof bar;
foo! in bar;

// Can be confusing with computed values
1 + foo.bar! == baz;
```

Example of **correct** code:
```ts
// Clear non-null assertions with parentheses
(foo.bar!) == baz;
(foo.bar!) === baz;
(foo!) instanceof bar;
(foo!) in bar;

// Negated tests are more clear
!(foo instanceof bar);
!(foo in bar);

// Assertions separated from comparison
const bar = foo.bar!;
bar === baz;

// No assertion needed if type is known
foo.bar === baz;
```