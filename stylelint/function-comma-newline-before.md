Pattern: Malformed newline before `,` in function

Issue: -

## Description

Require a newline or disallow whitespace before the commas of functions.

## Examples

### `"always"`

There *must always* be a newline before the commas.

The following patterns are considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
```

```css
a { transform: translate(1,
  1) }
```

The following patterns are *not* considered violations:

```css
a {
  transform: translate(1
    ,1)
}
```

```css
a {
  transform: translate(1
    , 1)
}
```

### `"always-multi-line"`

There *must always* be a newline before the commas in multi-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1,
  1) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
```

```css
a {
  transform: translate(1
    ,1)
}
```

```css
a {
  transform: translate(1
    , 1)
}
```

### `"never-multi-line"`

There *must never* be a whitespace before the commas in multi-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1 ,
  1) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1 ,1) }
```

```css
a { transform: translate(1 , 1) }
```

```css
a {
  transform: translate(1,
    1)
}
```

## Further Reading

* [stylelint - function-comma-newline-before](https://stylelint.io/user-guide/rules/function-comma-newline-before)