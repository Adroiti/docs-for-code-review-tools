Pattern: Malformed `v-else` directive

Issue: -

## Description

This rule reports `v-else` directives in the following cases:

- The directive has that argument. E.g. `<div v-if="foo"></div><div v-else:aaa></div>`
- The directive has that modifier. E.g. `<div v-if="foo"></div><div v-else.bbb></div>`
- The directive has that attribute value. E.g. `<div v-if="foo"></div><div v-else="bar"></div>`
- The directive is on the elements that the previous element don't have `v-if`/`v-else-if` directives. E.g. `<div v-else></div>`
- The directive is on the elements which have `v-if`/`v-else-if` directives. E.g. `<div v-if="foo" v-else></div>`

<eslint-code-block :rules="{'vue/valid-v-else': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-if="foo"/>
  <div v-else/>

  <!-- ✗ BAD -->
  <div v-else="foo"/>
  <div v-else:aaa/>
  <div v-else.bbb/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-else](https://eslint.vuejs.org/rules/valid-v-else.html)
