Pattern: Incorrect spacing after media query list comma

Issue: -

## Description

Require a single space or disallow whitespace after the commas of media query lists.

```css
@media screen and (color), projection and (color) {}
/**                      ↑
 * The space after this comma */
```

## Examples

`string`: `"always"|"never"|"always-single-line"|"never-single-line"`

### `"always"`

There _must always_ be a single space after the commas.

The following patterns are considered problems:

```css
@media screen and (color),projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

### `"never"`

There _must never_ be whitespace after the commas.

The following patterns are considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color),projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

### `"always-single-line"`

There _must always_ be a single space after the commas in single-line media query lists.

The following patterns are considered problems:

```css
@media screen and (color),projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

### `"never-single-line"`

There _must never_ be whitespace after the commas in single-line media query lists.

The following patterns are considered problems:

```css
@media screen and (color), projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color),projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

## Further Reading

* [stylelint - media-query-list-comma-space-after](https://stylelint.io/user-guide/rules/media-query-list-comma-space-after)