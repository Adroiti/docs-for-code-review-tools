Pattern: Malformed `v-bind` directive

Issue: -

## Description

This rule reports `v-bind` directives in the following cases:

- The directive does not have that attribute value. E.g. `<div v-bind:aaa></div>`
- The directive has invalid modifiers. E.g. `<div v-bind:aaa.bbb="ccc"></div>`

This rule does not report `v-bind` directives which do not have their argument (E.g. `<div v-bind="aaa"></div>`) because it's valid if the attribute value is an object.

<eslint-code-block :rules="{'vue/valid-v-bind': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-bind="foo"/>
  <div v-bind:aaa="foo"/>
  <div :aaa="foo"/>
  <div :aaa.prop="foo"/>

  <!-- ✗ BAD -->
  <div v-bind/>
  <div :aaa/>
  <div v-bind:aaa.bbb="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-bind](https://eslint.vuejs.org/rules/valid-v-bind.html)
