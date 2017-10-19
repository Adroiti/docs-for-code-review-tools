Pattern: Invalid custom media query name

Issue: -

## Description

Specify a pattern for custom media query names.

## Examples

`regex|string`

A string will be translated into a RegExp like so `new RegExp(someString)` — so be sure to escape properly.

Given the string:

```js
"foo-.+"
```

The following patterns are considered violations:

```css
@custom-media --bar (min-width: 30em);
```

The following patterns are *not* considered violations:

```css
@custom-media --foo-bar (min-width: 30em);
```

## Further Reading

* [stylelint - custom-media-pattern](https://stylelint.io/user-guide/rules/custom-media-pattern)