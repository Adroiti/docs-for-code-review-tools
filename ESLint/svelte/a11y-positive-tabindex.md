Pattern: Use of positive `tabindex` value

Issue: -

## Description

Avoid positive `tabindex` property values. This will move elements out of the expected tab order, creating a confusing experience for keyboard users.

```sv
<!-- A11y: avoid tabindex values above zero -->
<div tabindex='1'/>
```

## Further Reading

* [ESLint - a11y-positive-tabindex](https://svelte.dev/docs#accessibility-warnings-a11y-positive-tabindex)