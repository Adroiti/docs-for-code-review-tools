Pattern: Invalid custom property name

Issue: -

## Description

Specify a pattern for custom properties.

## Examples

`regex|string`

A string will be translated into a RegExp like so `new RegExp(someString)` — so be sure to escape properly.

Given the string:

```js
"foo-.+"
```

The following patterns are considered violations:

```css
:root { --boo-bar: 0; }
```

The following patterns are *not* considered violations:

```css
:root { --foo-bar: 0; }
```

## Further Reading

* [stylelint - custom-property-pattern](https://stylelint.io/user-guide/rules/custom-property-pattern)