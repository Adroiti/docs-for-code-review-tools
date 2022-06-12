Pattern: Missing simple/complex notation for `:not()`

Issue: -

## Description

Specify simple or complex notation for `:not()` pseudo-classes.

<!-- prettier-ignore -->
```css
    a:not(.foo, .bar) {}
/**  ↑
 * This notation */
```

In Selectors Level 3, only a single _simple selector_ was allowed as the argument to `:not()`, whereas Selectors Level 4 allows a _selector list_.

Use:

- `"complex"` to author modern Selectors Level 4 CSS
- `"simple"` for backwards compatibility with older browsers

## Examples

`string`: `"simple"|"complex"`

### `"simple"`

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
:not(a, div) {}
```

<!-- prettier-ignore -->
```css
:not(a.foo) {}
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
:not(a):not(div) {}
```

<!-- prettier-ignore -->
```css
:not(a) {}
```

### `"complex"`

The following pattern is considered a problem:

<!-- prettier-ignore -->
```css
:not(a):not(div) {}
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
:not(a, div) {}
```

<!-- prettier-ignore -->
```css
:not(a.foo) {}
```

<!-- prettier-ignore -->
```css
:not(a).foo:not(:empty) {}
```

## Further Reading

* [stylelint - selector-not-notation](https://stylelint.io/user-guide/rules/list/selector-not-notation)