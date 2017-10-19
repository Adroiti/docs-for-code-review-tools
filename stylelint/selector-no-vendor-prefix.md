Pattern: Unexpected vendor-prefix selector

Issue: -

## Description

This rule uses [Autoprefixer's](https://github.com/postcss/autoprefixer) up-to-date data (from [caniuse.com](http://caniuse.com/)) to know whether a vendor prefix should cause a violation or not. 

If you've included a vendor prefixed selector that has a standard alternative, one that Autoprefixer could take care of for you, this rule will complain about it. If, however, you use a non-standard vendor-prefixed selector, one that Autoprefixer would ignore and could not provide, this rule will ignore it.

## Examples

The following patterns are considered violations:

```css
input::-moz-placeholder {}
/**     ↑
 * These prefixes */
```

```css
:-webkit-full-screen a {}
```

The following patterns are *not* considered violations:

```css
input::placeholder {}
```

```css
:full-screen a {}
```

## Further Reading

* [stylelint - selector-no-vendor-prefix](https://stylelint.io/user-guide/rules/selector-no-vendor-prefix)