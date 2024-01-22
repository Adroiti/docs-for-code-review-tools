Pattern: Malformed whitespace after `,` in function

Issue: -

## Description

Require a single space or disallow whitespace after the commas of functions.

## Examples

### `"always"`

There *must always* be a single space after the commas.

The following patterns are considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1 , 1) }
```

### `"never"`

There *must never* be whitespace after the commas.

The following patterns are considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1 , 1) }
```

The following patterns are *not* considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
```

### `"always-single-line"`

There *must always* be a single space after the commas in single-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1,1) }
```

```css
a { transform: translate(1 ,1) }
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

### `"never-single-line"`

There *must never* be whitepace after the commas in single-line functions.

The following patterns are considered violations:

```css
a { transform: translate(1, 1) }
```

```css
a { transform: translate(1 , 1) }
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
    , 1)
}
```

## Further Reading

* [stylelint - function-comma-space-after](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/function-comma-space-after)