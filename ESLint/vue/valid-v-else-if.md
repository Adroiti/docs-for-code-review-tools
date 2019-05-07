Pattern: valid v else if

Issue: -

## Description

This rule reports `v-else-if` directives in the following cases:

- The directive has that argument. E.g. `<div v-if="foo"></div><div v-else-if:aaa="bar"></div>`
- The directive has that modifier. E.g. `<div v-if="foo"></div><div v-else-if.bbb="bar"></div>`
- The directive does not have that attribute value. E.g. `<div v-if="foo"></div><div v-else-if></div>`
- The directive is on the elements that the previous element don't have `v-if`/`v-else-if` directives. E.g. `<div v-else-if="bar"></div>`
- The directive is on the elements which have `v-if`/`v-else` directives. E.g. `<div v-if="foo" v-else-if="bar"></div>`

<eslint-code-block :rules="{'vue/valid-v-else-if': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-if="foo"/>
  <div v-else-if="bar"/>

  <!-- ✗ BAD -->
  <div v-else-if/>
  <div v-else-if:aaa="foo"/>
  <div v-else-if.bbb="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-else-if](https://eslint.vuejs.org/rules/valid-v-else-if.html)
