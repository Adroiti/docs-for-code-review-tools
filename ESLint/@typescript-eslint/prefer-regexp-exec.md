Pattern: String match over RegExp exec

Issue: -

## Description

When using regular expressions without the global flag, `String#match` and `RegExp#exec` are functionally identical. However, using `RegExp#exec` consistently makes code more readable and can be slightly faster. This applies only to non-global regular expressions; when using the global flag, `String#match` has different behavior.

## Examples

Example of **incorrect** code:
```ts
'something'.match(/thing/);

'some things are just things'.match(/thing/);

const text = 'something';
const search = /thing/;
text.match(search);
```

Example of **correct** code:
```ts
/thing/.exec('something');

// When using global flag, match is fine
'some things are just things'.match(/thing/g);

const text = 'something';
const search = /thing/;
search.exec(text);
```