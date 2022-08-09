Pattern: Unsupported ARIA attribute

Issue: -

## Description

Certain reserved DOM elements do not support ARIA roles, states and properties. This is often because they are not visible, for example `meta`, `html`, `script`, `style`. This rule enforces that these DOM elements do not contain the `aria-*` props.

```sv
<!-- A11y: <meta> should not have aria-* attributes -->
<meta aria-hidden="false">
```

## Further Reading

* [ESLint - a11y-aria-attributes](https://svelte.dev/docs#accessibility-warnings-a11y-aria-attributes)