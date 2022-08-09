Pattern: Misplaced `scope` attribute

Issue: -

## Description

The scope attribute should only be used on `<th>` elements.

```sv
<!-- A11y: The scope attribute should only be used with <th> elements -->
<div scope="row" />
```

## Further Reading

* [ESLint - a11y-misplaced-scope](https://svelte.dev/docs#accessibility-warnings-a11y-misplaced-scope)