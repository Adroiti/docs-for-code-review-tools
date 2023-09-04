Pattern: Malformed whitespace after `:` of declaration

Issue: -

## Description

Require a single space or disallow whitespace after the colon of declarations.

## Examples

### `"always"`

There *must always* be a single space after the colon.

The following patterns are considered violations:

```css
a { color :pink }
```

```css
a { color:pink }
```

The following patterns are *not* considered violations:

```css
a { color : pink }
```

```css
a { color: pink }
```

### `"never"`

There *must never* be whitespace after the colon.

The following patterns are considered violations:

```css
a { color:pink }
```

```css
a { color :pink }
```

The following patterns are *not* considered violations:

```css
a { color :pink }
```

```css
a { color:pink }
```

### `"always-single-line"`

There *must always* be a single space after the colon *if the declaration's value is single-line*.

The following patterns are considered violations:

```css
a {
  box-shadow:0 0 0 1px #5b9dd9, 0 0 2px 1px rgba(30, 140, 190, 0.8);
}
```

The following patterns are *not* considered violations:

```css
a {
  box-shadow: 0 0 0 1px #5b9dd9, 0 0 2px 1px rgba(30, 140, 190, 0.8);
}
```

```css
a {
  box-shadow:
    0 0 0 1px #5b9dd9,
    0 0 2px 1px rgba(30, 140, 190, 0.8);
}
```

```css
a {
  box-shadow:0 0 0 1px #5b9dd9,
    0 0 2px 1px rgba(30, 140, 190, 0.8);
}
```

## Further Reading

* [stylelint - declaration-colon-space-after](https://stylelint.io/user-guide/rules/declaration-colon-space-after)