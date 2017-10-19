Pattern: Malformed whitespace after `:` in media feature

Issue: -

## Description

Require a single space or disallow whitespace after the colon in media features.

## Examples

### `"always"`

There *must always* be a single space after the colon.

The following patterns are considered violations:

```css
@media (max-width:600px) {}
```

```css
@media (max-width :600px) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width: 600px) {}
```

```css
@media (max-width : 600px) {}
```

### `"never"`

There *must never* be whitespace after the colon.

The following patterns are considered violations:

```css
@media (max-width: 600px) {}
```

```css
@media (max-width : 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width:600px) {}
```

```css
@media (max-width :600px) {}
```

## Further Reading

* [stylelint - media-feature-colon-space-after](https://stylelint.io/user-guide/rules/media-feature-colon-space-after)