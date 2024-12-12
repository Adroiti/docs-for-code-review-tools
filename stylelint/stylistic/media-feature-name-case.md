Pattern: Malformed case for media feature name

Issue: -

## Description

Specify lowercase or uppercase for media feature names.

```css
@media (min-width: 700px) {}
/**     ↑
 * This media feature name */
```

## Examples

`string`: `"lower"|"upper"`

### `"lower"`

The following patterns are considered problems:

```css
@media (MIN-WIDTH: 700px) {}
```

```css
@media not all and (MONOCHROME) {}
```

```css
@media (min-width: 700px) and (ORIENTATION: landscape) {}
```

```css
@media (WIDTH > 10em) {}
```

The following patterns are _not_ considered problems:

```css
@media (min-width: 700px) {}
```

```css
@media not all and (monochrome) {}
```

```css
@media (min-width: 700px) and (orientation: landscape) {}
```

```css
@media (width > 10em) {}
```

### `"upper"`

The following patterns are considered problems:

```css
@media (min-width: 700px) {}
```

```css
@media not all and (monochrome) {}
```

```css
@media (MIN-WIDTH: 700px) and (orientation: landscape) {}
```

```css
@media (10em < width <= 50em) {}
```

The following patterns are _not_ considered problems:

```css
@media (MIN-WIDTH: 700px) {}
```

```css
@media not all and (MONOCHROME) {}
```

```css
@media (MIN-WIDTH: 700px) and (ORIENTATION: landscape) {}
```

```css
@media (10em < WIDTH <= 50em) {}
```

## Further Reading

* [stylelint - media-feature-name-case](https://stylelint.io/user-guide/rules/media-feature-name-case)