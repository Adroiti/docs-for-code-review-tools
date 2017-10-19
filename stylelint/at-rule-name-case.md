Pattern: Inconsistent at-rule name case

Issue: -

## Description

Specify lowercase or uppercase for at-rules names. This rule ignores `@import` in Less. Only lowercase at-rule names are valid in SCSS.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
@Charset 'UTF-8';
```

```css
@cHarSeT 'UTF-8';
```

```css
@CHARSET 'UTF-8';
```

```css
@Media (min-width: 50em) {}
```

```css
@mEdIa (min-width: 50em) {}
```

```css
@MEDIA (min-width: 50em) {}
```

The following patterns are *not* considered violations:

```css
@charset 'UTF-8';
```

```css
@media (min-width: 50em) {}
```

### `"upper"`

The following patterns are considered violations:

```css
@Charset 'UTF-8';
```

```css
@cHarSeT 'UTF-8';
```

```css
@charset 'UTF-8';
```

```css
@Media (min-width: 50em) {}
```

```css
@mEdIa (min-width: 50em) {}
```

```css
@media (min-width: 50em) {}
```

The following patterns are *not* considered violations:

```css
@CHARSET 'UTF-8';
```

```css
@MEDIA (min-width: 50em) {}
```

## Further Reading

* [stylelint - at-rule-name-case](https://stylelint.io/user-guide/rules/at-rule-name-case)