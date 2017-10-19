Pattern: Too many types in a selector

Issue: -

## Description

This rule resolves nested selectors before counting the number of type selectors. Each selector in a [selector list](https://www.w3.org/TR/selectors4/#selector-list) is evaluated separately.

The `:not()` pseudo-class is also evaluated separately. The rule processes the argument as if it were an independent selector, and the result does not count toward the total for the entire selector.

## Examples

`int`: Maximum type selectors allowed.

For example, with `2`:

The following patterns are considered violations:

```css
div a span {}
```

```css
div a {
  & span {}
}
```

```css
div a {
  & > a {}
}
```

The following patterns are *not* considered violations:

```css
div {}
```

```css
div a {}
```

```css
.foo div a {}
```

```css
div.foo a {}
```

```css
/* each selector in a selector list is evaluated separately */
div,
a span {}
```

```css
/* `span` is inside `:not()`, so it is evaluated separately */
div a .foo:not(span) {}
```

The following patterns are *not* considered violations:

# Configuration

### `ignore: ["child", "compounded", "descendant"]`

#### `"child"`

Discount child type selectors.

For example, with `2`:

The following patterns are *not* considered violations:

```css
div span > a {}
```

```css
#bar div span > a {}
```

#### `"compounded"`

Discount compounded type selectors -- i.e. type selectors chained with other selectors.

For example, with `2`:

The following patterns are *not* considered violations:

```css
div span a.foo {}
```

```css
div span a#bar {}
```

#### `"descendant"`

Discount descendant type selectors.

For example, with `2`:

The following patterns are *not* considered violations:

```css
.foo div span a {}
```

```css
#bar div span a {}
```

### `ignoreTypes: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom"]
```

For example, with `2`.

The following patterns are *not* considered violations:

```css
div a custom {}
```

```css
div a some-type {}
```

```css
div a some-other-type {}
```

## Further Reading

* [stylelint - selector-max-type](https://stylelint.io/user-guide/rules/selector-max-type)