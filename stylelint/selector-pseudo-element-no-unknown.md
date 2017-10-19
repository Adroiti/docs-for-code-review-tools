Pattern: Unknown pseudo-element selector

Issue: -

## Description

This rule considers pseudo-element selectors defined in the CSS Specifications, up to and including Editor's Drafts, to be known.

All vendor-prefixed pseudo-element selectors are ignored.

## Examples

The following patterns are considered violations:

```css
a::pseudo {}
```

```css
a::PSEUDO {}
```

```css
a::element {}
```

The following patterns are *not* considered violations:

```css
a:before {}
```

```css
a::before {}
```

```css
::selection {}
```

```css
input::-moz-placeholder {}
```

# Configuration

### `ignorePseudoElements: ["/regex/", "string"]`

Given:

```js
["/^some-/", "pseudo-element"]
```

The following patterns are *not* considered violations:

```css
a::pseudo-element {}
```

```css
a::some-pseudo {}
```

```css
a::some-other-pseudo {}
```

## Further Reading

* [stylelint - selector-pseudo-element-no-unknown](https://stylelint.io/user-guide/rules/selector-pseudo-element-no-unknown)