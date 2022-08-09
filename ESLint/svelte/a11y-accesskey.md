Pattern: Use of `accesskey` on element

Issue: -

## Description

Enforce no `accesskey` on element. Access keys are HTML attributes that allow web developers to assign keyboard shortcuts to elements. Inconsistencies between keyboard shortcuts and keyboard commands used by screen reader and keyboard-only users create accessibility complications. To avoid complications, access keys should not be used.

```sv
<!-- A11y: Avoid using accesskey -->
<div 
```

## Further Reading

* [ESLint - a11y-accesskey](https://svelte.dev/docs#accessibility-warnings-a11y-accesskey)