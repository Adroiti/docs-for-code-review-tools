Pattern: Unknown pseudo-class selector

Issue: -

## Description

Disallow unknown pseudo-class selectors. This rule considers pseudo-class selectors defined in the CSS Specifications, up to and including Editor's Drafts, to be known.

All vendor-prefixed pseudo-class selectors are ignored.

## Examples

The following patterns are considered violations:

```css
a:unknown {}
```

```css
a:UNKNOWN {}
```

```css
a:hoverr {}
```

The following patterns are *not* considered violations:

```css
a:hover {}
```

```css
a:focus {}
```

```css
:not(p) {}
```

```css
input:-moz-placeholder {}
```

# Configuration

### `ignorePseudoClasses: ["/regex/", "string"]`

Given:

```js
["/^some-/", "pseudo-class"]
```

The following patterns are *not* considered violations:

```css
a:pseudo-class {}
```

```css
a:some-pseudo {}
```

```css
a:some-other-pseudo {}
```

## Further Reading

* [stylelint - selector-pseudo-class-no-unknown](https://stylelint.io/user-guide/rules/selector-pseudo-class-no-unknown)