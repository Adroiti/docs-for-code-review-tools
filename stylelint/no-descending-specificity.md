Pattern: Confusing CSS prioritization

Issue: -

## Description

Source order is important in CSS, and when two selectors have the *same* specificity, the one that occurs *last* will take priority. However, the situation is different when one of the selectors has a *higher* specificity. In that case, source order does *not* matter: the selector with higher specificity will win out even if it comes first.

The clashes of these two mechanisms for prioritization, source order and specificity, can cause some confusion when reading stylesheets. If a selector with higher specificity comes *before* the selector it overrides, we have to think harder to understand it, because it violates the source order expectation. **Stylesheets are most legible when overriding selectors always come *after* the selectors they override.** That way both mechanisms, source order and specificity, work together nicely.

This rule enforces that practice *as best it can*. (It cannot catch every *actual* overriding selector (because it does not know the DOM structure, for one), but it can catch certain common mistakes.)

## Examples

The following patterns are considered violations:

```css
    #container a { top: 10px; } a { top: 0; }
/** ↑                           ↑
 * The order of these selectors represents descending specificity */
```

```css
b a {}
a {}
```

```css
a + a {}
a {}
```

```css
b > a[foo] {}
a[foo] {}
```

```css
a {
  & > b {}
}
b {}
```

```css
@media print {
  #c a {}
  a {}
}
```

The following patterns are *not* considered violations:

```css
a {}
b a {}
```

```css
a {}
a + a {}
```

```css
a[foo] {}
b > a[foo] {}
```

```css
b {}
a {
  & > b {}
}
```

```css
a::before {}
a:hover::before {}
a {}
a:hover {}
```

```css
@media print {
  a {}
  #c a {}
}
```

```css
a {}
@media print {
  #baz a {}
}
```

## Further Reading

* [stylelint - no-descending-specificity](https://stylelint.io/user-guide/rules/no-descending-specificity)