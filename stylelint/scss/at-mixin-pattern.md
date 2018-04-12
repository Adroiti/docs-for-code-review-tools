Pattern: Unexpected `@mixin` name

Issue: -

## Description

Specify a pattern for Sass/SCSS-like mixin names.

```scss
@mixin complex-object ($items: 10) {
/**    ↑
 * The pattern of this */
```

## Examples

`regex` or `string`

A string will be translated into a RegExp like so `new RegExp(yourString)` — so be sure to escape properly.

### E.g. `/foo-.+/`

The following patterns are considered warnings:

```scss
@mixin boo-bar {
```

The following patterns are *not* considered warnings:

```scss
@mixin foo-bar {
```

## Further Reading

* [stylelint-scss - at-mixin-pattern](https://github.com/kristerkari/stylelint-scss/blob/master/src/rules/at-mixin-pattern/README.md)