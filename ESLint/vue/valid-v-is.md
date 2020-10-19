Pattern: Use of invalid `v-is` directive

Issue: -

## Description

This rule reports `v-is` directives in the following cases:

- The directive has that argument. E.g. `<div v-is:aaa="foo"></div>`
- The directive has that modifier. E.g. `<div v-is.bbb="foo"></div>`
- The directive does not have that attribute value. E.g. `<div v-is></div>`
- The directive is on Vue-components. E.g. `<MyComponent v-is="foo"></MyComponent>`

<eslint-code-block :rules="{'vue/valid-v-is': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <tr v-is="'blog-post-row'"></tr>
  <tr v-is="foo"></tr>

  <!-- ✗ BAD -->
  <tr v-is:a="foo"></tr>
  <tr v-is.m="foo"></tr>
  <tr v-is></tr>
  <tr v-is=""></tr>
  <MyComponent v-is="foo" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-is](https://eslint.vuejs.org/rules/valid-v-is.html)
* [API - v-is](https://v3.vuejs.org/api/directives.html#v-is)
