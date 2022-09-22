Pattern: Text is too wide

Issue: -

## Description

Requires width of text greater than 45 characters and less than 80 characters.

## Examples


The following pattern are considered violations:

```css
.foo {
  text-transform: lowercase;
  max-width: 40ch;
}
```

```css
.foo {
  line-height: 1.8;
  max-width: 82ch;
}
```

The following patterns are _not_ considered violations:

```css
.foo {
  max-width: 65ch;
}
```

```css
.foo {
  max-width: 82ch;
}
```

```css
.foo {
  max-width: 100px;
}
```