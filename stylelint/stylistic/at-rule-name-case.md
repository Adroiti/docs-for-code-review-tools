Pattern: Incorrect case for at-rule name

Issue: -

## Description

Specify lowercase or uppercase for at-rules names.

```css
   @media (min-width: 10px) {}
/** ↑
 * This at-rule name */
```

Only lowercase at-rule names are valid in SCSS.

## Examples

`string`: `"lower"|"upper"`

### `"lower"`

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

```css
@charset 'UTF-8';
```

```css
@media (min-width: 50em) {}
```

### `"upper"`

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

```css
@CHARSET 'UTF-8';
```

```css
@MEDIA (min-width: 50em) {}
```

## Further Reading

* [stylelint - at-rule-name-case](https://stylelint.io/user-guide/rules/at-rule-name-case)