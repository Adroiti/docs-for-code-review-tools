Pattern: Malformed whitespace after range operator in media feature

Issue: -

## Description

Require a single space or disallow whitespace after the range operator in media features.

## Examples

### `"always"`

There *must always* be a single space after the range operator.

The following patterns are considered violations:

```css
@media (width>=600px) {}
```

```css
@media (width >=600px) {}
```

The following patterns are *not* considered violations:

```css
@media (width>= 600px) {}
```

```css
@media (width >= 600px) {}
```

### `"never"`

There *must never* be whitespace after the range operator.

The following patterns are considered violations:

```css
@media (width>= 600px) {}
```

```css
@media (width >= 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (width>=600px) {}
```

```css
@media (width >=600px) {}
```

## Further Reading

* [stylelint - media-feature-range-operator-space-after](https://stylelint.io/user-guide/rules/media-feature-range-operator-space-after)