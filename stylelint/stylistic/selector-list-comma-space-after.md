Pattern: Malformed whitespace after `,` in selector list

Issue: -

## Description

Require a single space or disallow whitespace after the commas of selector lists.

## Examples

### `"always"`

There *must always* be a single space after the commas.

The following patterns are considered violations:

```css
a,b { color: pink; }
```

```css
a ,b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a, b { color: pink; }
```

```css
a , b { color: pink; }
```

### `"never"`

There *must never* be whitespace after the commas.

The following patterns are considered violations:

```css
a, b { color: pink; }
```

```css
a , b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a,b { color: pink; }
```

```css
a ,b { color: pink; }
```

### `"always-single-line"`

There *must always* be a single space after the commas in single-line selector lists.

The following patterns are considered violations:

```css
a,b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a
,b { color: pink; }
```

### `"never-single-line"`

There *must never* be a single space after the commas in single-line selector lists.

The following patterns are considered violations:

```css
a, b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a
, b { color: pink; }
```

## Further Reading

* [stylelint - selector-list-comma-space-after](https://stylelint.io/user-guide/rules/selector-list-comma-space-after)