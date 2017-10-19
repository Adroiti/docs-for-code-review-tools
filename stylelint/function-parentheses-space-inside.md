Pattern: Malformed whitespace in function parentheses

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the parentheses of functions.

## Examples

### `"always"`

There *must always* be a single space inside the parentheses.

The following patterns are considered violations:

```css
a { transform: translate(1, 1); }
```

```css
a { transform: translate(1, 1 ); }
```

The following patterns are *not* considered violations:

```css
a { transform: translate( 1, 1 ); }
```

### `"never"`

There *must never* be whitespace on the inside the parentheses.

The following patterns are considered violations:

```css
a { transform: translate( 1, 1 ); }
```

```css
a { transform: translate(1, 1 ); }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1, 1); }
```

### `"always-single-line"`

There *must always* be a single space inside the parentheses of single-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1, 1 ) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate( 1, 1 ) }
```

```css
a { transform: translate(1,
  1) }
```

```css
a {
  transform: translate(
    1,
    1
  )
}
```

### `"never-single-line"`

There *must never* be whitespace inside the parentheses of single-line functions.

The following patterns are considered violations:

```css
a { transform: translate( 1, 1 ) }
```

```css
a { transform: translate(1, 1 ) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate( 1,
  1) }
```

```css
a {
  transform: translate(
    1,
    1
  )
}
```

## Further Reading

* [stylelint - function-parentheses-space-inside](https://stylelint.io/user-guide/rules/function-parentheses-space-inside)