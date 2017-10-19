Pattern: Unexpected non-space character

Issue: -

## Description

This rule ensures that only a single space is used and ensures no tabs, newlines, nor multiple spaces are used for descendant combinators of selectors.

## Examples

The following patterns are considered violations:

```css
.foo  .bar {}
```

```css
.foo
.bar {}
```

The following patterns are *not* considered violations:

```css
.foo .bar {}
```

## Further Reading

* [stylelint - selector-descendant-combinator-no-non-space](https://stylelint.io/user-guide/rules/selector-descendant-combinator-no-non-space)