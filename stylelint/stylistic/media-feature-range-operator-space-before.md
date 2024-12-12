Pattern: Incorrect spacing before range operator in media feature

Issue: -

## Description

Require a single space or disallow whitespace before the range operator in media features.

```css
@media (width >= 600px) {}
/**           ↑
 * The space before this operator */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space before the range operator.

The following patterns are considered problems:

```css
@media (width>=600px) {}
```

```css
@media (width>= 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (width >=600px) {}
```

```css
@media (width >= 600px) {}
```

### `"never"`

There _must never_ be whitespace before the range operator.

The following patterns are considered problems:

```css
@media (width >=600px) {}
```

```css
@media (width >= 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (width>=600px) {}
```

```css
@media (width>= 600px) {}
```

## Further Reading

* [stylelint - media-feature-range-operator-space-before](https://stylelint.io/user-guide/rules/media-feature-range-operator-space-before)