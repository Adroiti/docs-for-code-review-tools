Pattern: Invalid `.sync` modifier

Issue: -

## Description

This rule reports `.sync` modifier on `v-bind` directives in the following cases:

- The `.sync` modifier does not have the attribute value which is valid as LHS. E.g. `<MyComponent v-bind:aaa.sync="foo() + bar()" />`
- The `.sync` modifier is on non Vue-components. E.g. `<input v-bind:aaa.sync="foo"></div>`
- The `.sync` modifier's reference is iteration variables. E.g. `<div v-for="x in list"><MyComponent v-bind:aaa.sync="x" /></div>`

<eslint-code-block :rules="{'vue/valid-v-bind-sync': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-bind:aaa.sync="foo"/>
  <MyComponent :aaa.sync="foo"/>

  <div v-for="todo in todos">
    <MyComponent v-bind:aaa.sync="todo.name"/>
    <MyComponent :aaa.sync="todo.name"/>
  </div>

  <!-- ✗ BAD -->
  <MyComponent v-bind:aaa.sync="foo + bar" />
  <MyComponent :aaa.sync="foo + bar" />

  <input v-bind:aaa.sync="foo">
  <input :aaa.sync="foo">

  <div v-for="todo in todos">
    <MyComponent v-bind:aaa.sync="todo" />
    <MyComponent :aaa.sync="todo" />
  </div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-bind-sync](https://eslint.vuejs.org/rules/valid-v-bind-sync.html)
