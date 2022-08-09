Pattern: Missing required ARIA prop

Issue: -

## Description

Elements with ARIA roles must have all required attributes for that role.

```sv
<!-- A11y: A11y: Elements with the ARIA role "checkbox" must have the following attributes defined: "aria-checked" -->
<span role="checkbox" aria-labelledby="foo" tabindex="0"></span>
```

## Further Reading

* [ESLint - a11y-role-has-required-aria-props](https://svelte.dev/docs#accessibility-warnings-a11y-role-has-required-aria-props)