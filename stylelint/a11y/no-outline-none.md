Pattern: Use of outline clearing

Issue: -

## Description

Disallows outline clearing.

**Sources:**

- [DON'T DO IT!](http://www.outlinenone.com/)
- [a11yproject](https://a11yproject.com/posts/never-remove-css-outlines/)
- [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)

## Examples

The following pattern are considered violations:

```css
.foo:focus {
  outline: 0;
}
```

```css
.bar:focus {
  outline: none;
}
```

```css
.baz:focus {
  outline: none;
  border: transparent;
}
```

```scss
.quux {
  .quuux:focus {
    outline: 0;
  }
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  outline: 0;
}
```

```scss
$primary-color: #333;
.bar:focus {
  outline: 1px solid $primary-color;
}
```

```css
.baz:focus {
  outline: 1px solid #333;
}
```

```css
.quux:focus {
  outline: 0;
  border: 1px solid #000;
}
```