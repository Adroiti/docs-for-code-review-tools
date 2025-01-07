Pattern: Missing use of logical CSS unit

Issue: -

## Description

This rule is responsible for checking that logical CSS units are used. Specifically, viewport units like `vw` and `vh` which stand for viewport width and viewport height respectively will not reflect different writing modes and directions. Instead, this rule will enforce the logical equivalents, `vi` and `vb`.

Example of **incorrect** code:

```css
body {
  max-block-size: 100vh; /* Will flag the physical use of viewport "height" */
}

.container {
  inline-size: clamp(
    10vw,
    100%,
    50vw
  ); /* Will flag the physical use of viewport "width" */
}
```

Example of **correct** code:

```css
body {
  max-block-size: 100vb;
}
```

## Further Reading

* [stylelint-plugin-logical-css](https://github.com/yuschick/stylelint-plugin-logical-css#pluginuse-logical-units)