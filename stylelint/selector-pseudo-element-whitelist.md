Pattern: Use of non-whitelisted pseudo-element selector

Issue: -

## Description

This rule ignores:

-   CSS2 pseudo-elements i.e. those prefixed with a single colon
-   selectors that use variable interpolation e.g. `::#{$variable} {}`

## Examples

`array|string|regex`: `["array", "of", "unprefixed", "pseudo-elements" or "regex"]|"pseudo-element"|/regex/`

Given:

```js
["before", "/^my-/i"]
```

The following patterns are considered violations:

```css
a::after {}
```

```css
a::not-my-pseudo-element {}
```

The following patterns are *not* considered violations:

```css
a::before {}
```

```css
a::my-pseudo-element {}
```

```css
a::MY-OTHER-pseudo-element {}
```

## Further Reading

* [stylelint - selector-pseudo-element-whitelist](https://stylelint.io/user-guide/rules/selector-pseudo-element-whitelist)