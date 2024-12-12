Pattern: Incorrect spacing after range operator in media feature

Issue: -

## Description

Require a single space or disallow whitespace after the range operator in media features.

```css
@media (width >= 600px) {}
/**           ↑
 * The space after this operator */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space after the range operator.

The following patterns are considered problems:

```css
@media (width>=600px) {}
```

```css
@media (width >=600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (width>= 600px) {}
```

```css
@media (width >= 600px) {}
```

### `"never"`

There _must never_ be whitespace after the range operator.

The following patterns are considered problems:

```css
@media (width>= 600px) {}
```

```css
@media (width >= 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (width>=600px) {}
```

```css
@media (width >=600px) {}
```

## Further Reading

* [stylelint - media-feature-range-operator-space-after](https://stylelint.io/user-guide/rules/media-feature-range-operator-space-after)