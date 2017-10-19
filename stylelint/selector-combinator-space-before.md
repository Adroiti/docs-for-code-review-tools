Pattern: Malformed whitespace before combinator of selector

Issue: -

## Description

Require a single space or disallow whitespace before the combinators of selectors.

Combinators are used to combine several different selectors into new and more specific ones. There are several types of combinators, including: child (`>`), adjacent sibling (`+`), general sibling (`~`), and descendant (which is represented by a blank space between two selectors).

The descendant combinator is *not* checked by this rule.

Also, `+` and `-` signs within `:nth-*()` arguments are not checked (e.g. `a:nth-child(2n+1)`).

## Examples

### `"always"`

There *must always* be a single space before the combinators.

The following patterns are considered violations:

```css
a+ b { color: pink; }
```

```css
a>b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a + b { color: pink; }
```

```css
a >b { color: pink; }
```

### `"never"`

There *must never* be whitespace before the combinators.

The following patterns are considered violations:

```css
a + b { color: pink; }
```

```css
a >b { color: pink; }
```

The following patterns are *not* considered violations:

```css
a+ b { color: pink; }
```

```css
a>b { color: pink; }
```

## Further Reading

* [stylelint - selector-combinator-space-before](https://stylelint.io/user-guide/rules/selector-combinator-space-before)