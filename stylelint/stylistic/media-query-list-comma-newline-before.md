Pattern: Incorrect newline before media query list comma

Issue: -

## Description

Require a newline or disallow whitespace before the commas of media query lists.

```css
    @media screen and (color)
    , projection and (color) {}
/** ↑
 * This comma */
```

## Examples

### `"always"`

There _must always_ be a newline before the commas.

The following patterns are considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color),
projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color)
,projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

### `"always-multi-line"`

There _must always_ be a newline before the commas in multi-line media query lists.

The following patterns are considered problems:

```css
@media screen and (color),
projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

### `"never-multi-line"`

There _must never_ be whitespace before the commas in multi-line media query lists.

The following patterns are considered problems:

```css
@media screen and (color)
,projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

The following patterns are _not_ considered problems:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color),
projection and (color) {}
```

## Further Reading

* [stylelint - media-query-list-comma-newline-before](https://stylelint.io/user-guide/rules/media-query-list-comma-newline-before)