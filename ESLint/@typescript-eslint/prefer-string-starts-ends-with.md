Pattern: String check without startsWith/endsWith

Issue: -

## Description

Using methods like `indexOf`, `charAt`, `slice`, or regular expressions to check string prefixes and suffixes is less readable than the dedicated `startsWith` and `endsWith` methods. These ES2015 methods provide clearer intent and more maintainable code.

## Examples

Example of **incorrect** code:
```ts
declare const foo: string;

// Checking start
foo[0] === 'b';
foo.charAt(0) === 'b';
foo.indexOf('bar') === 0;
foo.slice(0, 3) === 'bar';
foo.substring(0, 3) === 'bar';
foo.match(/^bar/) != null;
/^bar/.test(foo);

// Checking end
foo[foo.length - 1] === 'b';
foo.charAt(foo.length - 1) === 'b';
foo.lastIndexOf('bar') === foo.length - 3;
foo.slice(-3) === 'bar';
foo.substring(foo.length - 3) === 'bar';
foo.match(/bar$/) != null;
/bar$/.test(foo);
```

Example of **correct** code:
```ts
declare const foo: string;

// Checking start
foo.startsWith('bar');

// Checking end
foo.endsWith('bar');

// When the logic is more complex than just starts/ends with
foo.indexOf('bar') > -1;
foo.match(/bar/) !== null;
```