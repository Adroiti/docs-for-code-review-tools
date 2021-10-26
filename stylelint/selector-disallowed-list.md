Pattern: Use of disallowed selector

Issue: -

## Description

Specify a list of disallowed selectors.

## Examples

Given:

```js
`["a > .foo", "/\\[data-.+]/"]`
```

The following patterns are considered problems:

```css
a > .foo {}
```

```css
a[data-auto="1"] {}
```

```css
.foo, [data-auto="1"] {}
```

The following patterns are *not* considered problems:

```css
.foo {}
```

```css
a
>
.foo {}
```

```css
.bar > a > .foo {}
```

## Further Reading

* [stylelint - selector-disallowed-list](https://stylelint.io/user-guide/rules/selector-disallowed-list)