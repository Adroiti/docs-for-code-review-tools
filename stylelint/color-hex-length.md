Pattern: Inconsistent hex color notation

Issue: -

## Description

Specify short or long notation for hex colors.

## Examples

### `"short"`

The following patterns are considered violations:

```css
a { color: #ffffff; }
```

```css
a { color: #ffffffaa; }
```

The following patterns are *not* considered violations:

```css
a { color: #fff; }
```

```css
a { color: #fffa; }
```

```css
a { color: #a4a4a4; }
```

### `"long"`

The following patterns are considered violations:

```css
a { color: #fff; }
```

```css
a { color: #fffa; }
```

The following patterns are *not* considered violations:

```css
a { color: #ffffff; }
```

```css
a { color: #ffffffaa; }
```

## Further Reading

* [stylelint - color-hex-length](https://stylelint.io/user-guide/rules/color-hex-length)