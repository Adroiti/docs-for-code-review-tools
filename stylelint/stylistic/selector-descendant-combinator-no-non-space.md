Pattern: Invalid character in descendant selector spacing

Issue: -

## Description

Disallow non-space characters for descendant combinators of selectors.

```css
.foo .bar .baz {}
/** ↑    ↑
* These descendant combinators */
```

This rule ensures that only a single space is used and ensures no tabs, newlines, nor multiple spaces are used for descendant combinators of selectors.

This rule currently ignores selectors containing comments.

## Examples

### `true`

The following patterns are considered problems:

```css
.foo  .bar {}
```

```css
.foo
.bar {}
```

The following patterns are _not_ considered problems:

```css
.foo .bar {}
```

## Further Reading

* [stylelint - selector-descendant-combinator-no-non-space](https://stylelint.io/user-guide/rules/selector-descendant-combinator-no-non-space)