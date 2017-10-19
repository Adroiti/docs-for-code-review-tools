Pattern: Malformed whitespace before `,` in media query list

Issue: -

## Description

Require a single space or disallow whitespace before the commas of media query lists.

## Examples

### `"always"`

There *must always* be a single space before the commas.

The following patterns are considered violations:

```css
@media screen and (color),projection and (color) {}
```

```css
@media screen and (color)
,projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color) ,projection and (color) {}
```

```css
@media screen and (color) ,
projection and (color) {}
```

### `"never"`

There *must never* be whitespace before the commas.

The following patterns are considered violations:

```css
@media screen and (color) ,projection and (color) {}
```

```css
@media screen and (color)
, projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color),projection and (color) {}
```

```css
@media screen and (color),
projection and (color) {}
```

### `"always-single-line"`

There *must always* be a single space before the commas in single-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color),projection and (color) {}
```

The following patterns are *not* considered violations:

```css
@media screen and (color) ,projection and (color) {}
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

There *must never* be whitespace before the commas in single-line media query lists.

The following patterns are considered violations:

```css
@media screen and (color) , projection and (color) {}
```

The following patterns are *not* considered violations:

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

* [stylelint - media-query-list-comma-space-before](https://stylelint.io/user-guide/rules/media-query-list-comma-space-before)