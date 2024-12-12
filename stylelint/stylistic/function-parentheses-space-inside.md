Pattern: Incorrect spacing inside function parentheses

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the parentheses of functions.

```css
a { transform: translate( 1, 1 ); }
/**                     ↑      ↑
 * The space inside these two parentheses */
```

## Examples

`string`: `"always"|"never"|"always-single-line"|"never-single-line"`

### `"always"`

There _must always_ be a single space inside of the parentheses.

The following patterns are considered problems:

```css
a { transform: translate(1, 1); }
```

```css
a { transform: translate(1, 1 ); }
```

The following patterns are _not_ considered problems:

```css
a { transform: translate( 1, 1 ); }
```

### `"never"`

There _must never_ be whitespace on the inside of the parentheses.

The following patterns are considered problems:

```css
a { transform: translate( 1, 1 ); }
```

```css
a { transform: translate(1, 1 ); }
```

The following patterns are _not_ considered problems:

```css
a { transform: translate(1, 1); }
```

### `"always-single-line"`

There _must always_ be a single space inside the parentheses of single-line functions.

The following patterns are considered problems:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1, 1 ) }
```

The following patterns are _not_ considered problems:

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

There _must never_ be whitespace inside the parentheses of single-line functions.

The following patterns are considered problems:

```css
a { transform: translate( 1, 1 ) }
```

```css
a { transform: translate(1, 1 ) }
```

The following patterns are _not_ considered problems:

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