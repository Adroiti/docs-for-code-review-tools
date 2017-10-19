Pattern: Malformed whitespace inside parentheses within media feature

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the parentheses within media features.

## Examples

### `"always"`

There *must always* be a single space inside the parentheses.

The following patterns are considered violations:

```css
@media (max-width: 300px) {}
```

```css
@media (max-width: 300px ) {}
```

The following patterns are *not* considered violations:

```css
@media ( max-width: 300px ) {}
```

### `"never"`

There *must never* be whitespace on the inside the parentheses.

The following patterns are considered violations:

```css
@media ( max-width: 300px ) {}
```

```css
@media ( max-width: 300px) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width: 300px) {}
```

## Further Reading

* [stylelint - media-feature-parentheses-space-inside](https://stylelint.io/user-guide/rules/media-feature-parentheses-space-inside)