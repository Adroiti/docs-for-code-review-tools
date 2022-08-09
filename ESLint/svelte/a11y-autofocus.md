Pattern: Use of `autofocus` on element

Issue: -

## Description

Enforce that `autofocus` is not used on elements. Autofocusing elements can cause usability issues for sighted and non-sighted users alike.

```sv
<!-- A11y: Avoid using autofocus -->
<input autofocus>
```

## Further Reading

* [ESLint - a11y-autofocus](https://svelte.dev/docs#accessibility-warnings-a11y-autofocus)