Pattern: Malformed newline before `,` in media query list

Issue: -

## Description

Require a newline or disallow whitespace before the commas of media query lists.

## Examples

### `"always"`

There *must always* be a newline before the commas.

The following patterns are considered violations:

```css
@media screen and (color), projection and (color) {}
```

```css
@media screen and (color),
projection and (color) {}
```

The following patterns are *not* considered violations:

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

There *must always* be a newline before the commas in multi-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color),
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

```css
@media screen and (color)
,
projection and (color) {}
```

### `"never-multi-line"`

There *must never* be whitespace before the commas in multi-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color)
,projection and (color) {}
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
@media screen and (color),
projection and (color) {}
```

## Further Reading

* [stylelint - media-query-list-comma-newline-before](https://stylelint.io/user-guide/rules/media-query-list-comma-newline-before)