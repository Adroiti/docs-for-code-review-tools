Pattern: Wrong component tags order

Issue: -

## Description

This rule warns about the order of the `<script>`, `<template>` & `<style>` tags.

## Options

```json
{
  "vue/component-tags-order": ["error", {
    "order": ["script", "template", "style"]
  }]
}
```

- `order` (`string[]`) ... The order of top-level element names. default `["script", "template", "style"]`.

### `{ "order": ["script", "template", "style"] }` (default)

<eslint-code-block :rules="{'vue/component-tags-order': ['error']}">

```vue
<!-- ✓ GOOD -->
<script>/* ... */</script>
<template>...</template>
<style>/* ... */</style>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/component-tags-order': ['error']}">

```vue
<!-- ✗ BAD -->
<style>/* ... */</style>
<script>/* ... */</script>
<template>...</template>
```

</eslint-code-block>

### `{ "order": ["template", "script", "style"] }`

<eslint-code-block :rules="{'vue/component-tags-order': ['error', { 'order': ['template', 'script', 'style'] }]}">

```vue
<!-- ✓ GOOD -->
<template>...</template>
<script>/* ... */</script>
<style>/* ... */</style>
```

</eslint-code-block>

### `{ "order": ["docs", "template", "script", "style"] }`

<eslint-code-block :rules="{'vue/component-tags-order': ['error', { 'order': ['docs', 'template', 'script', 'style'] }]}">

```vue
<!-- ✓ GOOD -->
<docs> documents </docs>
<template>...</template>
<script>/* ... */</script>
<style>/* ... */</style>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/component-tags-order': ['error', { 'order': ['docs', 'template', 'script', 'style'] }]}">

```vue
<!-- ✗ BAD -->
<template>...</template>
<script>/* ... */</script>
<docs> documents </docs>
<style>/* ... */</style>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - component-tags-order](https://eslint.vuejs.org/rules/component-tags-order.html)
