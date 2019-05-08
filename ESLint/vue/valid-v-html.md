Pattern: Malformed `v-html` directive

Issue: -

## Description

This rule reports `v-html` directives in the following cases:

- The directive has that argument. E.g. `<div v-html:aaa></div>`
- The directive has that modifier. E.g. `<div v-html.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-html></div>`

<eslint-code-block :rules="{'vue/valid-v-html': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-html="foo"/>

  <!-- ✗ BAD -->
  <div v-html/>
  <div v-html:aaa="foo"/>
  <div v-html.bbb="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-html](https://eslint.vuejs.org/rules/valid-v-html.html)
