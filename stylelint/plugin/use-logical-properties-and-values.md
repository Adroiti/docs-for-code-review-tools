Pattern: Missing use of logical property/value

Issue: -

## Description

Enforce the use of logical CSS properties and values.

Example of **incorrect** code:

```css
.heading {
  max-width: 90ch; /* Will flag the use of "width" */
  text-align: left; /* Will flag the use of "left" */
  opacity: 1;
  transition:
    opacity 1s ease,
    max-width 1s ease; /* Will flag the use of 'max-width' */
}
```

Example of **correct** code:

```css
.heading {
  max-inline-size: 90ch;
  text-align: start;
  opacity: 1;
  transition: opacity 1s ease, max-inline-size: 1s ease;
}
```

## Further Reading

* [stylelint-plugin-logical-css](https://github.com/yuschick/stylelint-plugin-logical-css#pluginuse-logical-properties-and-values)