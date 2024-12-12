Pattern: Missing newline after at-rule semicolon

Issue: -

## Description

Require a newline after the semicolon of at-rules.

```css
@import url("x.css");
@import url("y.css");
/**                 ↑
 * The newline after these semicolons */
```

This rule allows an end-of-line comment followed by a newline. For example:

```css
@import url("x.css"); /* end-of-line comment */

a {}
```

## Examples

`string`: `"always"`

### `"always"`

There _must always_ be a newline after the semicolon.

The following patterns are considered problems:

```css
@import url("x.css"); @import url("y.css");
```

```css
@import url("x.css"); a {}
```

The following patterns are _not_ considered problems:

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