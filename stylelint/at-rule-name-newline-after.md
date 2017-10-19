Pattern: Missing newline after at-rule name

Issue: -

## Description

Require a newline after at-rule names. This rule ignores `@import` in Less.

## Examples

### `"always"`

There *must always* be a newline after at-rule names.

The following patterns are considered violations:

```css
@charset "UTF-8";
```

```css
@media (min-width: 700px) and
  (orientation: landscape) {}
```

The following patterns are *not* considered violations:

```css
@charset
  "UTF-8";
```

```css
@import
  "x.css" screen and
 (orientation:landscape);
```

```css
@media
  (min-width: 700px) and (orientation: landscape) {}
```

```css
@media
  (min-width: 700px) and
  (orientation: landscape) {}
```

### `"always-multi-line"`

There *must always* be a newline after at-rule names in at-rules with multi-line parameters.

The following patterns are considered violations:

```css
@import "x.css" screen and
 (orientation:landscape);
```

```css
@media (min-width: 700px) and
 (orientation: landscape) {}
```

The following patterns are *not* considered violations:

```css
@charset "UTF-8";
```

```css
@charset
  "UTF-8";
```

```css
@import "x.css" screen and (orientation:landscape);
```

```css
@media (min-width: 700px) and (orientation: landscape) {}
```

```css
@media
  (min-width: 700px) and
  (orientation: landscape) {}
```

## Further Reading

* [stylelint - at-rule-name-newline-after](https://stylelint.io/user-guide/rules/at-rule-name-newline-after)