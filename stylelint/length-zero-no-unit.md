Pattern: Use of units for zero length

Issue: -

## Description

*Lengths* refer to distance measurements. A length is a *dimension*, which is a *number* immediately followed by a *unit identifier*. However, for zero lengths the unit identifier is optional. The length units are: `em`, `ex`, `ch`, `vw`, `vh`, `cm`, `mm`, `in`, `pt`, `pc`, `px`, `rem`, `vmin`, and `vmax`.

## Examples

The following patterns are considered violations:

```css
a { top: 0px; }
/**      ↑↑
 * This zero and this type of length unit */
```

```css
a { top: 0.000em }
```

The following patterns are *not* considered violations:

```css
a { top: 0 } /* no unit */
```

```css
a { transition-delay: 0s; } /* dimension */
```

```css
a { top: 2in; }
```

```css
a { top: 1.001vh }
```

# Configuration

### `ignore: ["custom-properties"]`

#### `"custom-properties"`

Ignore units for zero length in custom properties.

The following pattern is *not* considered a violation:

```css
a { --x: 0px; }
```

## Further Reading

* [stylelint - length-zero-no-unit](https://stylelint.io/user-guide/rules/length-zero-no-unit)