Pattern: Malformed ARIA value

Issue: -

## Description

Enforce that only the correct type of value is used for aria attributes. For example, `aria-hidden`
should only receive a boolean.

```sv
<!-- A11y: The value of 'aria-hidden' must be exactly one of true or false -->
<div aria-hidden="yes"/>
```

## Further Reading

* [ESLint - a11y-incorrect-aria-attribute-type](https://svelte.dev/docs#accessibility-warnings-a11y-incorrect-aria-attribute-type)