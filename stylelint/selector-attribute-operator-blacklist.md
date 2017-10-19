Pattern: Use of blacklisted attribute operator

Issue: -

## Description

Specify a blacklist of disallowed attribute operators.

## Examples

`array|string`: `["array", "of", "operators"]|"operator"`

Given:

```js
[ "*=" ]
```

The following patterns are considered violations:

```css
[class*="test"] {}
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

* [stylelint - selector-attribute-operator-blacklist](https://stylelint.io/user-guide/rules/selector-attribute-operator-blacklist)