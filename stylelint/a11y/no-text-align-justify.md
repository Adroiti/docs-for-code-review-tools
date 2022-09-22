Pattern: Use of `text-align: justify`

Issue: -

## Description

Disallows `{ text-align: justify; }` anywhere.

**Sources:**

- [W3C](https://www.w3.org/TR/WCAG20-TECHS/G169.html)
- [Design for Hackers](https://designforhackers.com/blog/justify-text-html-css/)

## Examples

The following pattern are considered violations:

```css
.foo {
  text-align: justify;
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  text-align: center;
}
```

```css
.foo {
  text-align: left;
}
```

```css
.foo {
  text-align: right;
}
```

```css
.foo {
  text-align: start;
}
```

```css
.foo {
  text-align: end;
}
```