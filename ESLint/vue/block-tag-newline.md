Pattern: Inconsistent block tag newline

Issue: -

## Description

This rule enforces a line break (or no line break) after opening and before closing block tags.

## Examples

```vue
<!-- ✓ GOOD -->
<template><input></template>

<script>
export default {}
</script>
```

```vue
<!-- ✗ BAD -->
<template>
<input></template>

<script>
export default {}</script>
```


## Further Reading

* [eslint-plugin-vue - block-tag-newline](https://eslint.vuejs.org/rules/block-tag-newline.html)
