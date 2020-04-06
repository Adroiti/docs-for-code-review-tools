Pattern: Malformed padding line between blocks

Issue: -

## Description

Requires or disallows blank lines between the given 2 blocks. Properly blank lines help developers to understand the code.

## Options

```json
{
  "vue/padding-line-between-blocks": ["error", "always" | "never"]
}
```

- `"always"` (default) ... Requires one or more blank lines. Note it does not count lines that comments exist as blank lines.
- `"never"` ... Disallows blank lines.

### `"always"` (default)

<eslint-code-block fix :rules="{'vue/padding-line-between-blocks': ['error']}">

```vue
<!-- ✓ GOOD -->
<template>
  <div></div>
</template>

<script>
export default {}
</script>

<style></style>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/padding-line-between-blocks': ['error']}">

```vue
<!-- ✗ BAD -->
<template>
  <div></div>
</template>
<script>
export default {}
</script>
<style></style>
```

</eslint-code-block>

### `"never"`

<eslint-code-block fix :rules="{'vue/padding-line-between-blocks': ['error', 'never']}">

```vue
<!-- ✓ GOOD -->
<template>
  <div></div>
</template>
<script>
export default {}
</script>
<style></style>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/padding-line-between-blocks': ['error', 'never']}">

```vue
<!-- ✗ BAD -->
<template>
  <div></div>
</template>

<script>
export default {}
</script>

<style></style>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - padding-line-between-blocks](https://eslint.vuejs.org/rules/padding-line-between-blocks.html)
