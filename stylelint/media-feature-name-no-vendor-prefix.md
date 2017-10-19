Pattern: Unexpected vendor-prefix for media feature name

Issue: -

## Description

Right now this rule simply checks for prefixed *resolutions*.

## Examples

The following patterns are considered violations:

```css
@media (-webkit-min-device-pixel-ratio: 1) {}
/**      ↑
 * This prefix */
```

```css
@media (min--mox-device-pixel-ratio: 1) {}
```

```css
@media (-o-max-device-pixel-ratio: 1/1) {}
```

The following patterns are *not* considered violations:

```css
@media (min-resolution: 96dpi) {}
```

```css
@media (max-resolution: 900dpi) {}
```

## Further Reading

* [stylelint - media-feature-name-no-vendor-prefix](https://stylelint.io/user-guide/rules/media-feature-name-no-vendor-prefix)