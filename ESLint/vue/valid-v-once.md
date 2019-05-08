Pattern: Malformed `v-once` directive

Issue: -

## Description

This rule reports `v-once` directives in the following cases:

- The directive has that argument. E.g. `<div v-once:aaa></div>`
- The directive has that modifier. E.g. `<div v-once.bbb></div>`
- The directive has that attribute value. E.g. `<div v-once="ccc"></div>`

<eslint-code-block :rules="{'vue/valid-v-once': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-once/>

  <!-- ✗ BAD -->
  <div v-once:aaa/>
  <div v-once.bbb/>
  <div v-once="ccc"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-once](https://eslint.vuejs.org/rules/valid-v-once.html)
