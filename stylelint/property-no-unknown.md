Pattern: Unknown CSS property

Issue: -

## Description

This rule considers properties defined in the [CSS Specifications and browser specific properties](https://github.com/betit/known-css-properties#source) to be known.

This rule ignores variables (`$sass`, `@less`, `--custom-property`).

This rule ignores vendor-prefixed properties (e.g., `-moz-align-self`, `-webkit-align-self`).
Use option `checkPrefixed` described below to turn on checking of vendor-prefixed properties.

## Examples

The following patterns are considered violations:

```css
a {
  colr: blue;
}
```

```css
a {
  some-property: 1;
}
```

The following patterns are *not* considered violations:

```css
a {
  color: green;
}
```

```css
a {
  fill: black;
}
```

```css
a {
  -moz-align-self: center;
}
```

```css
a {
  -webkit-align-self: center;
}
```

```css
a {
  align-self: center;
}
```

# Configuration

### `ignoreProperties: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom"]
```

The following patterns are *not* considered violations:

```css
a {
  some-property: 10px;
}
```

```css
a {
  some-other-property: 10px;
}
```

```css
a {
  custom: 10px;
}
```

### `checkPrefixed: true | false` (default: `false`)

If `true`, this rule will check vendor-prefixed properties.

For example with `true`:

The following patterns are *not* considered violations:

```css
a {
  -webkit-overflow-scrolling: auto;
}
```

```css
a {
  -moz-box-flex: 0;
}
```

The following patterns are considered  violations:

```css
a {
  -moz-align-self: center;
}
```

```css
a {
  -moz-overflow-scrolling: center;
}
```

## Further Reading

* [stylelint - property-no-unknown](https://stylelint.io/user-guide/rules/property-no-unknown)