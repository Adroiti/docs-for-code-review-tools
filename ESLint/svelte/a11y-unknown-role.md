Pattern: Unknown ARIA role

Issue: -

## Description

Elements with ARIA roles must use a valid, non-abstract ARIA role. A reference to role definitions can be found at [WAI-ARIA](https://www.w3.org/TR/wai-aria/#role_definitions) site.

```sv
<!-- A11y: Unknown role 'toooltip' (did you mean 'tooltip'?) -->
<div role="toooltip"></div>
```

## Further Reading

* [ESLint - a11y-unknown-role](https://svelte.dev/docs#accessibility-warnings-a11y-unknown-role)