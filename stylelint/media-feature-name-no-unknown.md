Pattern: Unknown media feature name

Issue: -

## Description

This rule considers media feature names defined in the CSS Specifications, up to and including Editor's Drafts, to be known.

All vendor-prefixed media feature names are ignored.

Caveat: Media feature names within a [range context](https://www.w3.org/TR/mediaqueries-4/#mq-ranges) are currently ignored.

## Examples

The following patterns are considered violations:

```css
@media screen and (unknown) {}
```

```css
@media screen and (unknown: 10px) {}
```

The following patterns are *not* considered violations:

```css
@media all and (monochrome) {}
```

```css
@media (min-width: 700px) {}
```

```css
@media (MIN-WIDTH: 700px) {}
```

```css
@media (min-width: 700px) and (orientation: landscape) {}
```

```css
@media (-webkit-min-device-pixel-ratio: 2) {}
```

# Configuration

### `ignoreMediaFeatureNames: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom"]
```

The following patterns are *not* considered violations:

```css
@media screen and (some-media-feature-name) {}
```

```css
@media screen and (custom: 10px) {}
```

```css
@media (min-width: 700px) and (custom: 10px) {}
```

## Further Reading

* [stylelint - media-feature-name-no-unknown](https://stylelint.io/user-guide/rules/media-feature-name-no-unknown)