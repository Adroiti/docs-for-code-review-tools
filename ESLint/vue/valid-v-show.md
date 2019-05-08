Pattern: Malformed `v-show` directive

Issue: -

## Description

This rule reports `v-show` directives in the following cases:

- The directive has that argument. E.g. `<div v-show:aaa></div>`
- The directive has that modifier. E.g. `<div v-show.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-show></div>`

<eslint-code-block :rules="{'vue/valid-v-show': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-show="foo"/>

  <!-- ✗ BAD -->
  <div v-show/>
  <div v-show:aaa="foo"/>
  <div v-show.bbb="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-show](https://eslint.vuejs.org/rules/valid-v-show.html)
