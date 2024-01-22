Pattern: Inconsistent hex color case

Issue: -

## Description

Specify lowercase or uppercase for hex colors.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
a { color: #FFF; }
```

The following patterns are *not* considered violations:

```css
a { color: #000; }
```

```css
a { color: #fff; }
```

### `"upper"`

The following patterns are considered violations:

```css
a { color: #fff; }
```

The following patterns are *not* considered violations:

```css
a { color: #000; }
```

```css
a { color: #FFF; }
```

## Further Reading

* [stylelint - color-hex-case](https://stylelint.io/user-guide/rules/color-hex-case)