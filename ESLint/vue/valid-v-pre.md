Pattern: Malformed `v-pre` directive

Issue: -

## Description

This rule reports `v-pre` directives in the following cases:

- The directive has that argument. E.g. `<div v-pre:aaa></div>`
- The directive has that modifier. E.g. `<div v-pre.bbb></div>`
- The directive has that attribute value. E.g. `<div v-pre="ccc"></div>`

<eslint-code-block :rules="{'vue/valid-v-pre': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-pre/>

  <!-- ✗ BAD -->
  <div v-pre:aaa/>
  <div v-pre.bbb/>
  <div v-pre="ccc"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-pre](https://eslint.vuejs.org/rules/valid-v-pre.html)
