Pattern: Incorrect newline after function `,`

Issue: -

## Description

Require a newline or disallow whitespace after the commas of functions.

```css
a { transform: translate(1,
  1) }                 /* ↑ */
/**                       ↑
 *             These commas */
```

## Examples

### `"always"`

There _must always_ be a newline after the commas.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

```css
a {
  transform: translate(1,
    1)
}
```

### `"always-multi-line"`

There _must always_ be a newline after the commas in multi-line functions.

The following patterns are considered problems:

```css
a { transform: translate(1
  ,1) }
```

The following patterns are _not_ considered problems:

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

There _must never_ be whitespace after the commas in multi-line functions.

The following patterns are considered problems:

```css
a { transform: translate(1
  , 1) }
```

The following patterns are _not_ considered problems:

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