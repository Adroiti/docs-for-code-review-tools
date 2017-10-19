Pattern: Use of non-whitelisted attribute operator

Issue: -

## Description

Specify a whitelist of allowed attribute operators.

## Examples

`array|string`: `["array", "of", "operators"]|"operator"`

Given:

```js
[ "=", "|=" ]
```

The following patterns are considered violations:

```css
[class*="test"] {}
```

```css
[title~="flower"] {}
```

```css
[class^="top"] {}
```

The following patterns are *not* considered violations:

```css
[target] {}
```

```css
[target="_blank"] {}
```

```css
[class|="top"] {}
```

## Further Reading

* [stylelint - selector-attribute-operator-whitelist](https://stylelint.io/user-guide/rules/selector-attribute-operator-whitelist)