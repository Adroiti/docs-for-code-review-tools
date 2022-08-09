Pattern: Misplaced `role` attribute

Issue: -

## Description

Certain reserved DOM elements do not support ARIA roles, states and properties. This is often because they are not visible, for example `meta`, `html`, `script`, `style`. This rule enforces that these DOM elements do not contain the `role` props.

```sv
<!-- A11y: <meta> should not have role attribute -->
<meta role="tooltip">
```

## Further Reading

* [ESLint - a11y-misplaced-role](https://svelte.dev/docs#accessibility-warnings-a11y-misplaced-role)