Pattern: Use of hidden element

Issue: -

## Description

Certain DOM elements are useful for screen reader navigation and should not be hidden.

```sv
<!-- A11y: <h2> element should not be hidden -->
<h2 aria-hidden="true">invisible header</h2>
```

## Further Reading

* [ESLint - a11y-hidden](https://svelte.dev/docs#accessibility-warnings-a11y-hidden)