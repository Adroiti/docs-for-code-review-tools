Pattern: Invalid id selector

Issue: -

## Description

Specify a pattern for id selectors.

## Examples

`regex|string`

A string will be translated into a RegExp — `new RegExp(someString)` — so *be sure to escape properly*.

The selector value *after `#`* will be checked. No need to include `#` in your pattern.

Given the string:

```js
"foo-[a-z]+"
```

The following patterns are considered violations:

```css
#foop {}
```

```css
#foo-BAR {}
```

```css
div > .zing + #foo-BAR {}
```

The following patterns are *not* considered violations:

```css
#foo-bar {}
```

```css
div > .zing + #foo-bar {}
```

```css
.foop {}
```

```css
[foo='bar'] {}
```

## Further Reading

* [stylelint - selector-id-pattern](https://stylelint.io/user-guide/rules/selector-id-pattern)