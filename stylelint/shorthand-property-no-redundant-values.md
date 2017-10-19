Pattern: Redundant value in shorthand property

Issue: -

## Description

This rule alerts you when you use redundant values in the following shorthand properties:

-   `margin`
-   `padding`
-   `border-color`
-   `border-radius`
-   `border-style`
-   `border-width`
-   `grid-gap`

## Examples

The following patterns are considered violations:

```css
a { margin: 1px 1px 1px 1px; }
/**             ↑   ↑   ↑
 *           These values */
```

```css
a { margin: 1px 1px; }
```

```css
a { padding: 1px 2px 1px; }
```

```css
a { border-radius: 1px 2px 1px 2px; }
```

```css
a { -webkit-border-radius: 1px 1px 1px 1px; }
```

The following patterns are *not* considered violations:

```css
a { margin: 1px; }
```

```css
a { margin: 1px 1px 1px 2px; }
```

```css
a { padding: 1px 1em 1pt 1pc; }
```

```css
a { border-radius: 10px / 5px; }
```

## Further Reading

* [stylelint - shorthand-property-no-redundant-values](https://stylelint.io/user-guide/rules/shorthand-property-no-redundant-values)