Pattern: Use of non-whitelisted combinator

Issue: -

## Description

This rule normalizes the whitespace descendant combinator to be a single space. It ignores [reference combinators](https://www.w3.org/TR/selectors4/#idref-combinators) e.g. `/for/`.

## Examples

`array|string`: `["array", "of", "combinators"]|"combinator"`

Given:

```js
[">", " "]
```

The following patterns are considered violations:

```css
a + b {}
```

```css
a ~ b {}
```

The following patterns are *not* considered violations:

```css
a > b {}
```

```css
a b {}
```

```css
a
b {}
```
