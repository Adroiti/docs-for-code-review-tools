Pattern: Use of restricted property

Issue: -

## Description

This rules enforces a blacklist of disallowed properties.

## Examples

`array|string`: `["array", "of", "unprefixed", "properties" or "regex"]|"property"|"/regex/"`

If a string is surrounded with `"/"` (e.g. `"/^background/"`), it is interpreted as a regular expression. This allows, for example, easy targeting of shorthands: `/^background/` will match `background`, `background-size`, `background-color`, etc.

Given:

```js
[ "text-rendering", "animation", "/^background/" ]
```

The following patterns are considered violations:

```css
a { text-rendering: optimizeLegibility; }
```

```css
a {
  animation: some-animation 2s;
  color: pink;
}
```

```css
a { -webkit-animation: some-animation 2s; }
```

```css
a { background: pink; }
```

```css
a { background-size: cover; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { no-background: sure; }
```

## Further Reading

* [stylelint - property-blacklist](https://stylelint.io/user-guide/rules/property-blacklist)