Pattern: Incorrect spacing after media feature `:`

Issue: -

## Description

Require a single space or disallow whitespace after the colon in media features.

```css
@media (max-width: 600px) {}
/**              ↑
 * The space after this colon */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space after the colon.

The following patterns are considered problems:

```css
@media (max-width:600px) {}
```

```css
@media (max-width :600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (max-width: 600px) {}
```

```css
@media (max-width : 600px) {}
```

### `"never"`

There _must never_ be whitespace after the colon.

The following patterns are considered problems:

```css
@media (max-width: 600px) {}
```

```css
@media (max-width : 600px) {}
```

The following patterns are _not_ considered problems:

```css
@media (max-width:600px) {}
```

```css
@media (max-width :600px) {}
```

## Further Reading

* [stylelint - media-feature-colon-space-after](https://stylelint.io/user-guide/rules/media-feature-colon-space-after)