Pattern: Missing percentage/number notation for alpha-value

Issue: -

## Description

Specify percentage or number notation for alpha-values.

## Examples

`string`: `"number"|"percentage"`

### `"number"`

Alpha-values _must always_ use the number notation.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { opacity: 50% }
```

<!-- prettier-ignore -->
```css
a { color: rgb(0 0 0 / 50%) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { opacity: 0.5 }
```

<!-- prettier-ignore -->
```css
a { color: rgb(0 0 0 / 0.5) }
```

### `"percentage"`

Alpha-values _must always_ use percentage notation.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { opacity: 0.5 }
```

<!-- prettier-ignore -->
```css
a { color: rgb(0 0 0 / 0.5) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { opacity: 50% }
```

<!-- prettier-ignore -->
```css
a { color: rgb(0 0 0 / 50%) }
```

## Further Reading

* [stylelint - alpha-value-notation](https://stylelint.io/user-guide/rules/alpha-value-notation)