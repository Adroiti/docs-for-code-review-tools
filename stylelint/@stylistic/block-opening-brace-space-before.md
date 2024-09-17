Pattern: Malformed whitespace before `{` of block

Issue: -

## Description

Require a single space or disallow whitespace before the opening brace of blocks.

## Examples

### `"always"`

There *must always* be a single space before the opening brace.

The following patterns are considered violations:

```css
a{ color: pink; }
```

```css
a
{ color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a {
color: pink; }
```

### `"never"`

There *must never* be whitespace before the opening brace.

The following patterns are considered violations:

```css
a { color: pink; }
```

```css
a
{ color: pink; }
```

The following patterns are *not* considered violations:

```css
a{ color: pink; }
```

```css
a{
color: pink; }
```

### `"always-single-line"`

There *must always* be a single space before the opening brace in single-line blocks.

The following patterns are considered violations:

```css
a{ color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a{
color: pink; }
```

### `"never-single-line"`

There *must never* be whitespace before the opening brace in single-line blocks.

The following patterns are considered violations:

```css
a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a{ color: pink; }
```

```css
a {
color: pink; }
```

### `"always-multi-line"`

There *must always* be a single space before the opening brace in multi-line blocks.

The following patterns are considered violations:

```css
a{
color: pink; }
```

The following patterns are *not* considered violations:

```css
a{ color: pink; }
```

```css
a {
color: pink; }
```

### `"never-multi-line"`

There *must never* be whitespace before the opening brace in multi-line blocks.

The following patterns are considered violations:

```css
a {
color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a{
color: pink;}
```

# Configuration

### `ignoreAtRules: ["/regex/", "non-regex"]`

Given:

```js
["/fo/"]
```

The following patterns are *not* considered violations:

```css
@for ...
{}
```

```css
@for ...{}
```

## Further Reading

* [stylelint - block-opening-brace-space-before](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/block-opening-brace-space-before)