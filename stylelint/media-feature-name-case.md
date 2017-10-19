Pattern: Inconsistent media feature name case

Issue: -

## Description

Specify lowercase or uppercase for media feature names. 

**Caveat:** Media feature names within a range context are currently ignored.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
@media (MIN-WIDTH: 700px) {}
```

```css
@media not all and (MONOCHROME) {}
```

```css
@media (min-width: 700px) and (ORIENTATION: landscape) {}
```

The following patterns are *not* considered violations:

```css
@media (min-width: 700px) {}
```

```css
@media not all and (monochrome) {}
```

```css
@media (min-width: 700px) and (orientation: landscape) {}
```

### `"upper"`

The following patterns are considered violations:

```css
@media (min-width: 700px) {}
```

```css
@media not all and (monochrome) {}
```

```css
@media (MIN-WIDTH: 700px) and (orientation: landscape) {}
```

The following patterns are *not* considered violations:

```css
@media (MIN-WIDTH: 700px) {}
```

```css
@media not all and (MONOCHROME) {}
```

```css
@media (MIN-WIDTH: 700px) and (ORIENTATION: landscape) {}
```

## Further Reading

* [stylelint - media-feature-name-case](https://stylelint.io/user-guide/rules/media-feature-name-case)