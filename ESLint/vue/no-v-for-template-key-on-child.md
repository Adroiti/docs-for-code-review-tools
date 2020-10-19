Pattern: Use of key of `<template v-for>` placed on child elements

Issue: -

## Description

This rule reports the key of the `<template v-for>` placed on the child elements.

In Vue.js 3.x, with the support for fragments, the `<template v-for>` key can be placed on the `<template>` tag. 

<eslint-code-block :rules="{'vue/no-v-for-template-key-on-child': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <template v-for="todo in todos" :key="todo">
    <Foo />
  </template>

  <!-- ✗ BAD -->
  <template v-for="todo in todos">
    <Foo :key="todo" />
  </template>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-v-for-template-key-on-child](https://eslint.vuejs.org/rules/no-v-for-template-key-on-child.html)
* [Migration Guide - `key` attribute > With `<template v-for>`](https://v3.vuejs.org/guide/migration/key-attribute.html#with-template-v-for)
