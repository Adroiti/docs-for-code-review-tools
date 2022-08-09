Pattern: Redundant ARIA role

Issue: -

## Description

Some HTML elements have default ARIA roles. Giving these elements an ARIA role that is already set by the browser [has no effect](https://www.w3.org/TR/using-aria/#aria-does-nothing) and is redundant.

```sv
<!-- A11y: Redundant role 'button' -->
<button role="button" />

<!-- A11y: Redundant role 'img' -->
<img role="img" src="foo.jpg" />
```

## Further Reading

* [ESLint - a11y-no-redundant-roles](https://svelte.dev/docs#accessibility-warnings-a11y-no-redundant-roles)