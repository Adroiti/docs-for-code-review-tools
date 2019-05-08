Pattern: Missing `v-bind:key` for `v-for` directive

Issue: -

## Description

This rule reports the elements which have `v-for` and do not have `v-bind:key` with exception to custom components.

<eslint-code-block :rules="{'vue/require-v-for-key': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    v-for="todo in todos"
    :key="todo.id"
  />
  <!-- ✗ BAD -->
  <div v-for="todo in todos"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-v-for-key](https://eslint.vuejs.org/rules/require-v-for-key.html)
