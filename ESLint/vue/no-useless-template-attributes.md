Pattern: Use of unnecessary attribute on `<template>`

Issue: -

## Description

Reports any useless attributes on `<template>` tags.

```vue
<template>
  <!-- ✓ GOOD -->
  <template v-if="foo">...</template>
  <template v-if="foo">...</template>
  <template v-else-if="foo">...</template>
  <template v-else>...</template>
  <template v-for="i in foo" :key="i">...</template>
  <template v-slot:foo>...</template>
  <!-- for Vue<=2.5 -->
  <template slot="foo">...</template>
  <template :slot="foo">...</template>
  <template slot-scope="param">...</template>
  <!-- for Vue<=2.4 -->
  <template scope="param">...</template>

  <!-- ✗ BAD -->
  <template v-if="foo" class="heading">...</template>
  <template v-for="i in foo" :bar="i">...</template>
  <template v-slot:foo="foo" ref="input">...</template>
  <template v-if="foo" @click="click">...</template>

  <!-- Ignore -->
  <template class="heading">...</template>
  <template :bar="i">...</template>
  <template ref="input">...</template>
  <template @click="click">...</template>
</template>
```

## Further Reading

* [eslint-plugin-vue - no-useless-template-attributes](https://eslint.vuejs.org/rules/no-useless-template-attributes.html)
