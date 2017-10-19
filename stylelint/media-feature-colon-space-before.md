Pattern: Malformed whitespace before `:` in media feature

Issue: -

## Description

Require a single space or disallow whitespace before the colon in media features.

## Examples

### `"always"`

There *must always* be a single space before the colon.

The following patterns are considered violations:

```css
@media (max-width:600px) {}
```

```css
@media (max-width: 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width :600px) {}
```

```css
@media (max-width : 600px) {}
```

### `"never"`

There *must never* be whitespace before the colon.

The following patterns are considered violations:

```css
@media (max-width :600px) {}
```

```css
@media (max-width : 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width:600px) {}
```

```css
@media (max-width: 600px) {}
```

## Further Reading

* [stylelint - media-feature-colon-space-before](https://stylelint.io/user-guide/rules/media-feature-colon-space-before)