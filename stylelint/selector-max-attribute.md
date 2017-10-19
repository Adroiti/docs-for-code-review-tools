Pattern: Too many attribute selectors

Issue: -

## Description

This rule resolves nested selectors before counting the number of attribute selectors. Each selector in a [selector list](https://www.w3.org/TR/selectors4/#selector-list) is evaluated separately.

The `:not()` pseudo-class is also evaluated separately. The rule processes the argument as if it were an independent selector, and the result does not count toward the total for the entire selector.

## Examples

`int`: Maximum attribute selectors allowed.

For example, with `2`:

The following patterns are considered violations:

```css
[type="number"][name="quality"][data-attribute="value"] {}
```

```css
[type="number"][name="quality"][disabled] {}
```

```css
[type="number"][name="quality"] {
  & [data-attribute="value"] {}
}
```

```css
[type="number"][name="quality"] {
  & [disabled] {}
}
```

```css
[type="number"][name="quality"] {
  & > [data-attribute="value"] {}
}
```

```css
/* `[type="text"][data-attribute="value"][disabled]` is inside `:not()`, so it is evaluated separately */
input:not([type="text"][data-attribute="value"][disabled]) {}
```

The following patterns are *not* considered violations:

```css
[type="text"] {}
```

```css
[type="text"][name="message"] {}
```

```css
[type="text"][disabled]
```

```css
/* each selector in a selector list is evaluated separately */
[type="text"][name="message"],
[type="number"][name="quality"] {}
```

```css
/* `[disabled]` is inside `:not()`, so it is evaluated separately */
[type="text"][name="message"]:not([disabled]) {}
```

# Configuration

### `ignoreAttributes: ["/regex/", "string"]`

Given:

```js
["/^some-/", "dir"]
```

For example, with `0`.

The following patterns are *not* considered violations:

```css
[dir] [some-attr] {}
```

```css
[dir] [some-other-attr] {}
```

## Further Reading

* [stylelint - selector-max-attribute](https://stylelint.io/user-guide/rules/selector-max-attribute)