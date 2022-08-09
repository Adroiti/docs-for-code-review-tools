Pattern: Malformed DOM element structure

Issue: -

## Description

Enforce that certain DOM elements have the correct structure.

```sv
<!-- A11y: <figcaption> must be an immediate child of <figure> -->
<div>
	<figcaption>Image caption</figcaption>
</div>
```

## Further Reading

* [ESLint - a11y-structure](https://svelte.dev/docs#accessibility-warnings-a11y-structure)