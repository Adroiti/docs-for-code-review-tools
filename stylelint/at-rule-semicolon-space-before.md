Pattern: Malformed whitespace before `;` of at-rule

Issue: -

## Description

This rule ignores `@import` in Less.

## Examples

### `"always"`

There *must always* be a single space before the semicolons.

The following patterns is considered a violation:

```css
@import "components/buttons";
```

The following pattern is *not* considered a violation:

```css
@import "components/buttons" ;
```

### `"never"`

There *must never* be a single space before the semicolons.

The following patterns is considered a violation:

```css
@import "components/buttons" ;
```

The following pattern is *not* considered a violation:

```css
@import "components/buttons";
```

## Further Reading

* [stylelint - at-rule-semicolon-space-before](https://stylelint.io/user-guide/rules/at-rule-semicolon-space-before)