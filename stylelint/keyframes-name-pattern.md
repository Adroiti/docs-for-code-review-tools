Pattern: Missing pattern for keyframe name

Issue: -

## Description

Specify a pattern for keyframe names.

## Examples

`regex|string`

A string will be translated into a RegExp — `new RegExp(yourString)` — so *be sure to escape properly*.

Given the string:

```js
"foo-.+"
```

The following patterns are considered violations:

```css
@keyframes foo {}
```

```css
@keyframes bar {}
```

```css
@keyframes FOO-bar {}
```

The following patterns are *not* considered violations:

```css
@keyframes foo-bar {}
```

## Further Reading

* [stylelint - keyframes-name-pattern](https://stylelint.io/user-guide/rules/keyframes-name-pattern)