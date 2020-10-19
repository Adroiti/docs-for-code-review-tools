Pattern: Use of deprecated `.sync` modifier on `v-bind`

Issue: -

## Description

This rule reports use of deprecated `.sync` modifier on `v-bind` directive (in Vue.js 3.0.0+).

<eslint-code-block fix :rules="{'vue/no-deprecated-v-bind-sync': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-bind:propName="foo"/>
  <MyComponent :propName="foo"/>


  <!-- ✗ BAD -->
  <MyComponent v-bind:propName.sync="foo"/>
  <MyComponent v-bind:[dynamiArg].sync="foo"/>
  <MyComponent v-bind.sync="foo"/>
  <MyComponent :propName.sync="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-v-bind-sync](https://eslint.vuejs.org/rules/no-deprecated-v-bind-sync.html)
* [Migration Guide - `v-model`](https://v3.vuejs.org/guide/migration/v-model.html)
* [Vue RFCs - 0005-replace-v-bind-sync-with-v-model-argument](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0005-replace-v-bind-sync-with-v-model-argument.md)
