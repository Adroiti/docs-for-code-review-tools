Pattern: Selector specificity is too high

Issue: -

## Description

Limit the specificity of selectors. Visit the [Specificity Calculator](https://specificity.keegan.st) for visual representation of selector specificity.

This rule ignores selectors with variable interpolation (`#{$var}`, `@{var}`, `$(var)`). This rule resolves nested selectors before calculating the specificity of a selector.

## Examples

`string`: Maximum specificity allowed.

Format is `"id,class,type"`, as laid out in the [W3C selector spec](https://drafts.csswg.org/selectors/#specificity-rules).

For example, with `"0,2,0"`:

The following patterns are considered violations:

```css
#foo {}
```

```css
.foo .baz .bar {}
```

```css
.foo .baz {
  & .bar {}
}
```

```css
.foo {
  color: red;
  @nest .baz .bar & {
    color: blue;
  }
}
```

The following patterns are *not* considered violations:

```css
div {}
```

```css
.foo div {}
```

```css
.foo div {
  & div a {}
}
```

```css
.foo {
  & .baz {}
}
```

```css
.foo {
  color: red;
  @nest .baz & {
    color: blue;
  }
}
```

# Configuration

### `ignoreSelectors: ["/regex/", "string"]`

Given:

```js
["0,2,0", {
  ignoreSelectors: [":global", ":local", "/some-/"]
}];
```

The following patterns are *not* considered violations:

```css
:global(.foo) .bar {}
```

```css
:local(.foo.bar)
```

```css
:local(.foo, :global(.bar).baz)
```

The following patterns are considered violations:

```css
:global(.foo) .bar.baz {}
```

```css
:local(.foo.bar.baz)
```

```css
:local(.foo, :global(.bar), .foo.bar.baz)
```

## Further Reading

* [stylelint - selector-max-specificity](https://stylelint.io/user-guide/rules/selector-max-specificity)