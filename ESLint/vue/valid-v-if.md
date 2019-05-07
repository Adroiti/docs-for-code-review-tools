Pattern: valid v if

Issue: -

## Description

This rule reports `v-if` directives in the following cases:

- The directive has that argument. E.g. `<div v-if:aaa="foo"></div>`
- The directive has that modifier. E.g. `<div v-if.bbb="foo"></div>`
- The directive does not have that attribute value. E.g. `<div v-if></div>`
- The directive is on the elements which have `v-else`/`v-else-if` directives. E.g. `<div v-else v-if="foo"></div>`

<eslint-code-block :rules="{'vue/valid-v-if': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-if="foo"/>
  <div v-else-if="bar"/>
  <div v-else/>

  <!-- ✗ BAD -->
  <div v-if/>
  <div v-if:aaa="foo"/>
  <div v-if.bbb="foo"/>
  <div
    v-if="foo"
    v-else
  />
  <div
    v-if="foo"
    v-else-if="bar"
  />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-if](https://eslint.vuejs.org/rules/valid-v-if.html)
