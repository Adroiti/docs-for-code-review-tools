Pattern: Malformed newline after `,` in media query list

Issue: -

## Description

Require a newline or disallow whitespace after the commas of media query lists.

## Examples

### `"always"`

There *must always* be a newline after the commas.

The following patterns are considered violations:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color),
projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

### `"always-multi-line"`

There *must always* be a newline after the commas in multi-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color)
, projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color),
projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

### `"never-multi-line"`

There *must never* be a white after the commas in multi-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color),
projection and (color) {}
```

```css
@media screen and (color)
,
projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

## Further Reading

* [stylelint - media-query-list-comma-newline-after](https://stylelint.io/user-guide/rules/media-query-list-comma-newline-after)