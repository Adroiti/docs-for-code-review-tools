Pattern: Invalid media query

Issue: -

## Description

Disallows invalid media queries.

Media queries must be grammatically valid according to the Media Queries Level 5 specification.

## Examples

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
@media not(min-width: 300px) {}

@media (width == 100px) {}

@media (color) and (hover) or (width) {}
```

The following patterns are *not* considered violations:

```css
@media not (min-width: 300px) {}

@media (width = 100px) {}

@media ((color) and (hover)) or (width) {}
```

## Further Reading

* [stylelint - media-query-no-invalid](https://stylelint.io/user-guide/rules/media-query-no-invalid)