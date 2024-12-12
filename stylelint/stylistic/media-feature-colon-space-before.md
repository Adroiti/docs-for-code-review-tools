Pattern: Incorrect spacing before media feature `:`

Issue: -

## Description

Require a single space or disallow whitespace before the colon in media features.

```css
@media (max-width :600px) {}
/**               ↑
 * The space before this colon */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space before the colon.

The following patterns are considered problems:

```css
@media (max-width:600px) {}
```

```css
@media (max-width: 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (max-width :600px) {}
```

```css
@media (max-width : 600px) {}
```

### `"never"`

There _must never_ be whitespace before the colon.

The following patterns are considered problems:

```css
@media (max-width :600px) {}
```

```css
@media (max-width : 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (max-width:600px) {}
```

```css
@media (max-width: 600px) {}
```

## Further Reading

* [stylelint - media-feature-colon-space-before](https://stylelint.io/user-guide/rules/media-feature-colon-space-before)