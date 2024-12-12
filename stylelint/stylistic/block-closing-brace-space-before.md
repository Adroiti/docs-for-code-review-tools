Pattern: Incorrect spacing before closing brace

Issue: -

## Description

Require a single space or disallow whitespace before the closing brace of blocks.

```css
a { color: pink; }
/**              ↑
 * The space before this brace */
```

## Examples

`string`: `"always"|"never"|"always-single-line"|"never-single-line"|"always-multi-line"|"never-multi-line"`

### `"always"`

There _must always_ be a single space before the closing brace.

The following patterns are considered problems:

```css
a { color: pink;}
```

```css
a
{ color: pink;}
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {
color: pink; }
```

### `"never"`

There _must never_ be whitespace before the closing brace.

The following patterns are considered problems:

```css
a { color: pink; }
```

```css
a
{ color: pink; }
```

The following patterns are _not_ considered problems:

```css
a{ color: pink;}
```

```css
a{
color: pink;}
```

### `"always-single-line"`

There _must always_ be a single space before the closing brace in single-line blocks.

The following patterns are considered problems:

```css
a { color: pink;}
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {
color: pink;}
```

### `"never-single-line"`

There _must never_ be whitespace before the closing brace in single-line blocks.

The following patterns are considered problems:

```css
a { color: pink; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink;}
```

```css
a {
color: pink; }
```

### `"always-multi-line"`

There _must always_ be a single space before the closing brace in multi-line blocks.

The following patterns are considered problems:

```css
a {
color: pink;}
```

The following patterns are _not_ considered problems:

```css
a { color: pink;}
```

```css
a {
color: pink; }
```

### `"never-multi-line"`

There _must never_ be whitespace before the closing brace in multi-line blocks.

The following patterns are considered problems:

```css
a {
color: pink; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {
color: pink;}
```

## Further Reading

* [stylelint - block-closing-brace-space-before](https://stylelint.io/user-guide/rules/block-closing-brace-space-before)