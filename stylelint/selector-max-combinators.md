Pattern: Too many combinators selectors

Issue: -

## Description

This rule resolves nested selectors before counting the number of combinators selectors. Each selector in a [selector list](https://www.w3.org/TR/selectors4/#selector-list) is evaluated separately.

## Examples

`int`: Maximum combinators selectors allowed.

For example, with `2`:

The following patterns are considered violations:

```css
a b ~ c + d {}
```

```css
a b ~ c {
  & > d {}
}
```

```css
a b {
  & ~ c {
    & + d {}
  }
}
```

The following patterns are *not* considered violations:

```css
a {}
```

```css
a b {}
```

```css
a b ~ c {}
```

```css
a b {
  & ~ c {}
}
```

```css
/* each selector in a selector list is evaluated separately */
a b,
c > d {}
```

## Further Reading

* [stylelint - selector-max-combinators](https://stylelint.io/user-guide/rules/selector-max-combinators)