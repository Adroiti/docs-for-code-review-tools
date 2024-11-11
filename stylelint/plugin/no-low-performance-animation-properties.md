Pattern: Use of low performance animation

Issue: -

## Description

This rule reports the use of low performance animation and transition properties.

Example of **incorrect** code:

```css
div {
  transition: margin-left 350ms ease-in;
}
```

Example of **correct** code:

```css
div {
  transition: transform 350ms ease-in;
}
```

## Further Reading

* [stylelint-high-performance-animation](https://github.com/kristerkari/stylelint-high-performance-animation?tab=readme-ov-file#details)