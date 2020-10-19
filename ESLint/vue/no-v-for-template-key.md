Pattern: Use of `<template v-for>` element with `key` attribute

Issue: -

## Description

This rule reports the `<template v-for>` elements which have `key` attribute.

In Vue.js 2.x, disallows `key` attribute on `<template>` elements.

<eslint-code-block :rules="{'vue/no-v-for-template-key': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <template v-for="item in list">
    <div :key="item.id" />
  </template>

  <!-- ✗ BAD -->
  <template v-for="item in list" :key="item.id">
    <div />
  </template>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-v-for-template-key](https://eslint.vuejs.org/rules/no-v-for-template-key.html)
* [API - Special Attributes - key](https://v3.vuejs.org/api/special-attributes.html#key)
* [API (for v2) - Special Attributes - key](https://vuejs.org/v2/api/#key)