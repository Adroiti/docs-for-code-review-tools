Pattern: Require a newline after `;` of at-rule

Issue: -

## Description

Require a newline after the semicolon of at-rules. This rule ignores `@import` in Less. This rule allows an end-of-line comment followed by a newline. For example:

```css
@import url("x.css"); /* end-of-line comment */

a {}
```

## Examples

### `"always"`

There *must always* be a newline after the semicolon.

The following patterns are considered violations:

```css
@import url("x.css"); @import url("y.css");
```

```css
@import url("x.css"); a {}
```

The following patterns are *not* considered violations:

```css
@import url("x.css");
@import url("y.css");
```

```css
@import url("x.css"); /* end-of-line comment */
a {}
```

```css
@import url("x.css");

a {}
```

## Further Reading

* [stylelint - at-rule-semicolon-newline-after](https://stylelint.io/user-guide/rules/at-rule-semicolon-newline-after)