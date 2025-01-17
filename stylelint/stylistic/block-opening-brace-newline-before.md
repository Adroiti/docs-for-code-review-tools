Pattern: Malformed newline before opening brace

Issue: -

## Description

Require a newline or disallow whitespace before the opening brace of blocks.

```css
  a
    { color: pink; }
/** ↑
 * The newline before this brace */
```

## Examples

`string`: `"always"|"always-single-line"|"never-single-line"|"always-multi-line"|"never-multi-line"`

### `"always"`

There _must always_ be a newline before the opening brace.

The following patterns are considered problems:

```css
a{ color: pink; }
```

```css
a{ color: pink;
}
```

The following patterns are _not_ considered problems:

```css
a
{ color: pink; }
```

```css
a
{
color: pink; }
```

```css
a /* foo */
  {
    color: pink;
  }
```

### `"always-single-line"`

There _must always_ be a newline before the opening brace in single-line blocks.

The following patterns are considered problems:

```css
a{ color: pink; }
```

The following patterns are _not_ considered problems:

```css
a
{ color: pink; }
```

```css
a{
color: pink; }
```

### `"never-single-line"`

There _must never_ be whitespace before the opening brace in single-line blocks.

The following patterns are considered problems:

```css
a { color: pink; }
```

The following patterns are _not_ considered problems:

```css
a{ color: pink; }
```

```css
a {
color: pink; }
```

### `"always-multi-line"`

There _must always_ be a newline before the opening brace in multi-line blocks.

The following patterns are considered problems:

```css
a{
color: pink; }
```

```css
a {
color: pink; }
```

The following patterns are _not_ considered problems:

```css
a{ color: pink; }
```

```css
a { color: pink; }
```

```css
a
{ color: pink; }
```

```css
a
{
color: pink; }
```

### `"never-multi-line"`

There _must never_ be whitespace before the opening brace in multi-line blocks.

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
a{
color: pink;}
```

## Further Reading

* [stylelint - block-opening-brace-newline-before](https://stylelint.io/user-guide/rules/block-opening-brace-newline-before)