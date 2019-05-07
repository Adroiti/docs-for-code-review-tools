Pattern: valid v text

Issue: -

## Description

This rule reports `v-text` directives in the following cases:

- The directive has that argument. E.g. `<div v-text:aaa></div>`
- The directive has that modifier. E.g. `<div v-text.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-text></div>`

<eslint-code-block :rules="{'vue/valid-v-text': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-text="foo"/>

  <!-- ✗ BAD -->
  <div v-text/>
  <div v-text:aaa="foo"/>
  <div v-text.bbb="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-text](https://eslint.vuejs.org/rules/valid-v-text.html)
