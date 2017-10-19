Pattern: Malformed newline after `,` in function

Issue: -

## Description

Require a newline or disallow whitespace after the commas of functions.

## Examples

### `"always"`

There *must always* be a newline after the commas.

The following patterns are considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
```

```css
a { transform: translate(1
  ,1) }
```

The following patterns are *not* considered violations:

```css
a {
  transform: translate(1,
    1)
}
```

### `"always-multi-line"`

There *must always* be a newline after the commas in multi-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1
  ,1) }
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
  transform: translate(1,
    1)
}
```

### `"never-multi-line"`

There *must never* be a whitespace after the commas in multi-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1
  , 1) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1 , 1) }
```

```css
a {
  transform: translate(1
    ,1)
}
```

## Further Reading

* [stylelint - function-comma-newline-after](https://stylelint.io/user-guide/rules/function-comma-newline-after)