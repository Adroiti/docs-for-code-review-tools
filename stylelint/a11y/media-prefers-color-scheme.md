Pattern: Missing use of `prefers-color-scheme`

Issue: -

## Description

Require implementation of certain styles for selectors with colors.

## Examples

The following pattern are considered violations:

```css
.foo {
  color: red;
}
```

```css
.bar {
  color: red;
}
.baz {
  background-color: red;
}
@media screen and (prefers-color-scheme: dark) {
  .baz {
    background-color: white;
  }
}
```

```css
.foo {
  color: red;
}
@media screen and (prefers-color-scheme: dark) {
  .foo {
    background-color: red;
  }
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  color: red;
}
@media screen and (prefers-color-scheme: dark) {
  .foo {
    color: white;
  }
}
```

```css
.bar {
  background-color: white;
}
@media screen and (prefers-color-scheme: dark) {
  .bar {
    background-color: gray;
  }
}
```