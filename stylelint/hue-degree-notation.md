Pattern: Missing number/angle notation for degree hue

Issue: -

## Description

Because hues are so often given in degrees, a hue can also be given as a number, which is interpreted as a number of degrees.

## Examples

`string`: `"angle"|"number"`

### `"angle"`

Degree hues _must always_ use angle notation.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { color: hsl(198 28% 50%) }
```

<!-- prettier-ignore -->
```css
a { color: lch(56.29% 19.86 10 / 15%) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { color: hsl(198deg 28% 50%) }
```

<!-- prettier-ignore -->
```css
a { color: lch(56.29% 19.86 10deg / 15%) }
```

### `"number"`

Degree hues _must always_ use the number notation.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { color: hsl(198deg 28% 50%) }
```

<!-- prettier-ignore -->
```css
a { color: lch(56.29% 19.86 10deg / 15%) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { color: hsl(198 28% 50%) }
```

<!-- prettier-ignore -->
```css
a { color: lch(56.29% 19.86 10 / 15%) }
```

## Further Reading

* [stylelint - hue-degree-notation](https://stylelint.io/user-guide/rules/hue-degree-notation)