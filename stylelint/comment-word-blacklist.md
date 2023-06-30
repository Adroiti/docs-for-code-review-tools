Pattern: Use of blacklisted word in comment

Issue: -

## Description

Specify a blacklist of disallowed words within comments. **Caveat:** Comments within *selector and value lists* are currently ignored.

## Examples

`array|string`: `["array", "of", "words", "or", "/regex/"]|"word"|"/regex/"`

If a string is surrounded with `"/"` (e.g. `"/^TODO:/"`), it is interpreted as a regular expression.

Given:

```js
["/^TODO:/", "badword"]
```

The following patterns are considered violations:

```css
/* TODO: */
```

```css
/* TODO: add fallback */
```

```css
/* some badword */
```

The following patterns are *not* considered violations:

```css
/* comment */
```
