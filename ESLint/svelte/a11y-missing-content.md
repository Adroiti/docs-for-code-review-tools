Pattern: Missing attribute content

Issue: -

## Description

Enforce that heading elements (`h1`, `h2`, etc.) and anchors have content and that the content is accessible to screen readers.

```sv
<!-- A11y: <a> element should have child content -->
<a href='/foo'></a>

<!-- A11y: <h1> element should have child content -->
<h1></h1>
```

## Further Reading

* [ESLint - a11y-missing-content](https://svelte.dev/docs#accessibility-warnings-a11y-missing-content)