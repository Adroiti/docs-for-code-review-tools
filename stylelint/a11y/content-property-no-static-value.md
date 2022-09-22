Pattern: Use of CSS-generated content

Issue: -

## Description

Disallows CSS generated content except aria-label attribute content and empty strings.

## Examples

The following pattern are considered violations:

```css
.foo::before {
  content: 'Price: $50';
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  content: '';
}
```

```css
.foo {
  content: attr(aria-label);
}
```