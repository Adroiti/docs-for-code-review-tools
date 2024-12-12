Pattern: Missing space after at-rule name

Issue: -

## Description

Require a single space after at-rule names.

```css
@media (max-width: 600px) {}
/**   ↑
 * The space after at-rule names */
```

## Examples

`string`: `"always"|"always-single-line"`

### `"always"`

There _must always_ be a single space after at-rule names.

The following patterns are considered problems:

```css
@charset"UTF-8";
```

```css
@media(min-width: 700px) {}
```

```css
@media  (min-width: 700px) {}
```

```css
@media
(min-width: 700px) {}
```

The following patterns are _not_ considered problems:

```css
@charset "UTF-8";
```

```css
@import url("x.css");
```

```css
@media (min-width: 700px) {}
```

### `"always-single-line"`

There _must always_ be a single space after at-rule names in single-line declaration blocks.

The following patterns are considered problems:

```css
@charset"UTF-8";
```

```css
@media(min-width: 700px) {}
```

```css
@media  (min-width: 700px) {}
```

The following patterns are _not_ considered problems:

```css
@charset "UTF-8";
```

```css
@import url("x.css");
```

```css
@media (min-width: 700px) {}
```

```css
@media
(min-width: 700px) {}
```

```css
@media(min-width: 700px) and
  (orientation: portrait) {}
```

```css
@media
  (min-width: 700px) and
  (orientation: portrait) {}
```

## Further Reading

* [stylelint - at-rule-name-space-after](https://stylelint.io/user-guide/rules/at-rule-name-space-after)