Pattern: Use of blacklisted at-rule

Issue: -

## Description

Specify a blacklist of disallowed at-rules. This rule ignores `@import` in Less.

## Examples

`array|string`: `["array", "of", "unprefixed", "at-rules"]|"at-rule"`

Given:

```js
["extend", "keyframes"]
```

The following patterns are considered violations:

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
@-moz-keyframes name {
  from { top: 10px; }
  to { top: 20px; }
}
```

The following patterns are *not* considered violations:

```css
@import "path/to/file.css";
```

## Further Reading

* [stylelint - at-rule-blacklist](https://stylelint.io/user-guide/rules/at-rule-blacklist)