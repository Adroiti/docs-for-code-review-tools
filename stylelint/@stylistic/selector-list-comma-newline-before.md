Pattern: Malformed newline before `,` in selector list

Issue: -

## Description

Require a newline or disallow whitespace before the commas of selector lists.

## Examples

### `"always"`

There *must always* be a newline before the commas.

The following patterns are considered violations:

```css
a, b { color: pink; }
```

```css
a,
b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a
, b { color: pink; }
```

```css
a
,b { color: pink; }
```

### `"always-multi-line"`

There *must always* be a newline before the commas in multi-line selector lists.

The following patterns are considered violations:

```css
a,
b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a, b { color: pink; }
```

```css
a
,b { color: pink; }
```

```css
a
,
b { color: pink; }
```

### `"never-multi-line"`

There *must never* be whitespace before the commas in multi-line selector lists.

The following patterns are considered violations:

```css
a
, b { color: pink; }
```

```css
a
,
b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a,b { color: pink; }
```

```css
a,
b { color: pink; }
```

## Further Reading

* [stylelint - selector-list-comma-newline-before](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/selector-list-comma-newline-before)