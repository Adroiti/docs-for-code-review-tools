Pattern: Missing use of `:focus`

Issue: -

## Description

Checks the presence of a pseudo-class for selectors with `:hover`.

```css
a:hover,
a:focus {
}
```

This rule considers :focus pseudo-class selector defined in the CSS Specifications.

## Examples

The following pattern are considered violations:

```css
a:hover {
}
```

The following patterns are _not_ considered violations:

```css
a:hover,
a:focus {
}
```

```css
a:focus {
}
```

```css
a:hover {
}
a:focus {
}
```