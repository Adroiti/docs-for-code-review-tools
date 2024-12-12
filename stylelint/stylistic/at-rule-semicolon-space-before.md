Pattern: Incorrect spacing before at-rule semicolon

Issue: -

## Description

Require a single space or disallow whitespace before the semicolons of at-rules.

```css
@import "components/buttons";
/**                         ↑
 * The space before this semicolon */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space before the semicolons.

The following pattern is considered a problem:

```css
@import "components/buttons";
```

The following pattern is _not_ considered a problem:

```css
@import "components/buttons" ;
```

### `"never"`

There _must never_ be a single space before the semicolons.

The following pattern is considered a problem:

```css
@import "components/buttons" ;
```

The following pattern is _not_ considered a problem:

```css
@import "components/buttons";
```

## Further Reading

* [stylelint - at-rule-semicolon-space-before](https://stylelint.io/user-guide/rules/at-rule-semicolon-space-before)