Pattern: Inconsistent hex color alpha channel

Issue: -

## Description

Require or disallow alpha channel for hex colors.

## Examples

### `"always"`

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
a { color: #fff; }
```

<!-- prettier-ignore -->
```css
a { color: #ffffff; }
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
a { color: #fffa; }
```

<!-- prettier-ignore -->
```css
a { color: #ffffffaa; }
```

### `"never"`

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
a { color: #fffa; }
```

<!-- prettier-ignore -->
```css
a { color: #ffffffaa; }
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
a { color: #fff; }
```

<!-- prettier-ignore -->
```css
a { color: #ffffff; }
```

## Further Reading

* [stylelint - color-hex-alpha](https://github.com/stylelint/stylelint/blob/main/lib/rules/color-hex-alpha/README.md)