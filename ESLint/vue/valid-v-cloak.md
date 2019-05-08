Pattern: Malformed `v-cloak` directive

Issue: -

## Description

This rule reports `v-cloak` directives in the following cases:

- The directive has that argument. E.g. `<div v-cloak:aaa></div>`
- The directive has that modifier. E.g. `<div v-cloak.bbb></div>`
- The directive has that attribute value. E.g. `<div v-cloak="ccc"></div>`

<eslint-code-block :rules="{'vue/valid-v-cloak': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-cloak/>

  <!-- ✗ BAD -->
  <div v-cloak:aaa/>
  <div v-cloak.bbb/>
  <div v-cloak="ccc"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-cloak](https://eslint.vuejs.org/rules/valid-v-cloak.html)
