Pattern: Malformed attribute value

Issue: -

## Description

Enforce that attributes important for accessibility have a valid value. For example, `href` should not be empty, `'#'`, or `javascript:`.

```sv
<!-- A11y: '' is not a valid href attribute -->
<a href=''>invalid</a>
```

## Further Reading

* [ESLint - a11y-invalid-attribute](https://svelte.dev/docs#accessibility-warnings-a11y-invalid-attribute)