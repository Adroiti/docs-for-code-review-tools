Pattern: Too many compound selectors

Issue: -

## Description

A [compound selector](https://www.w3.org/TR/selectors4/#compound) is a chain of one or more simple (tag, class, id, universal, attribute) selectors. If there is more than one compound selector in a complete selector, they will be separated by combinators (e.g. ` `, `+`, `>`). One reason why you might want to limit the number of compound selectors is described in the [SMACSS book](https://smacss.com/book/applicability).

This rule resolves nested selectors before calculating the depth of a selector.

`:not()` is considered one compound selector irrespective to the complexity of the selector inside it. The rule *does* process that inner selector, but does so separately, independent of the main selector.

## Examples

`int`: Maximum compound selectors allowed.

For example, with `3`:

The following patterns are considered violations:

```css
.foo .bar .baz .lorem {}
```

```css
.foo .baz {
  & > .bar .lorem {}
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
#foo #bar > #baz {}
```

```css
.foo + div :not (a b ~ c) {} /* `a b ~ c` is inside :not() and is processed separately */
```

## Further Reading

* [stylelint - selector-max-compound-selectors](https://stylelint.io/user-guide/rules/selector-max-compound-selectors)