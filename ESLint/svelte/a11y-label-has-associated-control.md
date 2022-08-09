Pattern: Malformed label tag

Issue: -

## Description

Enforce that a label tag has a text label and an associated control.

There are two supported ways to associate a label with a control:

- Wrapping a control in a label tag.
- Adding `for` to a label and assigning it the ID of an input on the page.

```sv
<label for="id">B</label>

<label>C <input type="text" /></label>

<!-- A11y: A form label must be associated with a control. -->
<label>A</label>
```

## Further Reading

* [ESLint - a11y-label-has-associated-control](https://svelte.dev/docs#accessibility-warnings-a11y-label-has-associated-control)