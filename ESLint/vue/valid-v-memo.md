Pattern: Malformed `v-memo` directive

Issue: -

## Description

Reports `v-memo` directives in the following cases:

- The directive has that argument. E.g. `<div v-memo:aaa></div>`
- The directive has that modifier. E.g. `<div v-memo.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-memo></div>`
- The attribute value of the directive is definitely not array. E.g. `<div v-memo="{x}"></div>`
- The directive was used inside v-for. E.g. `<div v-for="i in items"><div v-memo="[i]" /></div>`

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-memo="[x]"/>

  <!-- ✗ BAD -->
  <div v-memo/>
  <div v-memo:aaa="[x]"/>
  <div v-memo.bbb="[x]"/>
  <div v-memo="{x}"/>
  <div v-for="i in items">
    <div v-memo="[i]" />
  </div>
</template>
```

## Further Reading

* [eslint-plugin-vue - valid-v-memo](https://eslint.vuejs.org/rules/valid-v-memo.html)
