Pattern: Out of gamut range color

Issue: -

## Description

Colors declared using lch, oklch, lab and oklab functions can move from sRGB to P3 or Rec2020 color spaces, which are not supported by most of screens right now. It can happen by mistake. For instance, by converting colors from one space to another.

This rule checks if the color is in sRGB, p3 or rec2020 space. If it's not in sRGB gamut you should wrap it in a proper media query:

```css
@media (color-gamut: p3) {
  a {
    color: lch(29.8% 42.5 109.485);
    /* This color is in p3 gamut range */
  }
}
```

```css
@media (color-gamut: rec2020) {
  a {
    color: lch(25.1% 42.5 109.485);
    /* This color is in rec2020 gamut range */
  }
}
```

In case of css custom properties you should wrap either the custom property declaration:

```css
@media (color-gamut: p3) {
  :root {
    --my-var: lch(48% 82 283);
  }
}
```

or the rule that uses the custom property:

```css
@media (color-gamut: p3) {
  a {
    color: var(--my-var);
  }
}
```


## Further Reading

* [color-no-out-gamut-range](https://github.com/fpetrakov/stylelint-gamut/blob/master/src/README.md)