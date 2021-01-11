Pattern: Use of non-allowed-listed media feature

Issue: -

## Description

This rules enforces a whitelist of allowed media feature names. **Caveat:** Media feature names within a range context are currently ignored.

## Examples

`array|string|regex`: `["array", "of", "unprefixed", "media-features" or "regex"]|"media-feature"|/regex/`

Given:

```js
["max-width", "/^some-/"]
```

The following patterns are considered violations:

```css
@media (min-width: 50em) {}
```

```css
@media print and (min-resolution: 300dpi) {}
```

The following patterns are *not* considered violations:

```css
@media (max-width: 50em) {}
```

```css
@media (some-width: 50em) {}
```

## Further Reading

* [stylelint - media-feature-name-allowed-list](https://stylelint.io/user-guide/rules/media-feature-name-allowed-list)