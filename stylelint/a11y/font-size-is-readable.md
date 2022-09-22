Pattern: Unreadable font size

Issue: -

## Description

Disallows font sizes less than 15px (or 11.25pt).

## Examples

The following pattern are considered violations:

```css
.foo {
  font-size: 10px;
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  font-size: 15px;
}
```

```css
.foo {
  font-size: 1em;
}
```