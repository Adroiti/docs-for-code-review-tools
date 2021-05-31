Pattern: Invalid `@import` position

Issue: -

## Description

Any `@import` rules must precede all other valid at-rules and style rules in a stylesheet (ignoring `@charset`), or else the `@import` rule is invalid.

## Examples

The following patterns are considered violations:

```css
a {}
@import 'foo.css';
```

```css
@media print {}
@import 'foo.css';
```

The following patterns are *not* considered violations:

```css
@import 'foo.css';
a {}
```

```css
/* some comment */
@import 'foo.css';
```

## Further Reading

* [stylelint - no-invalid-position-at-import-rule](https://stylelint.io/user-guide/rules/no-invalid-position-at-import-rule)