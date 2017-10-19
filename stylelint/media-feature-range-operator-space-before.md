Pattern: Malformed whitespace before range operator in media feature

Issue: -

## Description

Require a single space or disallow whitespace before the range operator in media features.

## Examples

### `"always"`

There *must always* be a single space before the range operator.

The following patterns are considered violations:

```css
@media (width>=600px) {}
```

```css
@media (width>= 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (width >=600px) {}
```

```css
@media (width >= 600px) {}
```

### `"never"`

There *must never* be whitespace before the range operator.

The following patterns are considered violations:

```css
@media (width >=600px) {}
```

```css
@media (width >= 600px) {}
```

The following patterns are *not* considered violations:

```css
@media (width>=600px) {}
```

```css
@media (width>= 600px) {}
```

## Further Reading

* [stylelint - media-feature-range-operator-space-before](https://stylelint.io/user-guide/rules/media-feature-range-operator-space-before)