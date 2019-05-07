Pattern: no template key

Issue: -

## Description

This rule reports the `<template>` elements which have `key` attribute.

<eslint-code-block :rules="{'vue/no-template-key': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div key="foo"> ... </div>
  <template> ... </template>

  <!-- ✗ BAD -->
  <template key="foo"> ... </template>
  <template v-bind:key="bar"> ... </template>
  <template :key="baz"> ... </template>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-template-key](https://eslint.vuejs.org/rules/no-template-key.html)
