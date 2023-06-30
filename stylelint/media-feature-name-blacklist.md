Pattern: Use of blacklisted media feature

Issue: -

## Description

**Caveat:** Media feature names within a range context are currently ignored.

## Examples

`array|string|regex`: `["array", "of", "unprefixed", "media-features" or "regex"]|"media-feature"|/regex/`

Given:

```js
["max-width", "/^some-/"]
```

The following patterns are considered violations:

```css
@media (max-width: 50em) {}
```

```css
@media (some-width: 50em) {}
```

The following patterns are *not* considered violations:

```css
@media (min-width: 50em) {}
```

```css
@media print and (min-resolution: 300dpi) {}
```
