Pattern: Use of non-whitelisted at-rule

Issue: -

## Description

Specify a whitelist of allowed at-rules. This rule ignores `@import` in Less.

## Examples

`array|string`: `["array", "of", "unprefixed", "at-rules"]|"at-rule"`

Given:

```js
["extend", "keyframes"]
```

The following patterns are considered violations:

```css
@import "path/to/file.css";
```

```css
@media screen and (max-width: 1024px) {
  a { display: none; }
}
```

The following patterns are *not* considered violations:

```css
a { @extend placeholder; }
```

```css
@keyframes name {
  from { top: 10px; }
  to { top: 20px; }
}
```

```css
@KEYFRAMES name {
  from { top: 10px; }
  to { top: 20px; }
}
```

```css
@-moz-keyframes name {
  from { top: 10px; }
  to { top: 20px; }
}

## Further Reading

* [stylelint - at-rule-whitelist](https://stylelint.io/user-guide/rules/at-rule-whitelist)