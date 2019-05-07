Pattern: valid v for

Issue: -

## Description

This rule reports `v-for` directives in the following cases:

- The directive has that argument. E.g. `<div v-for:aaa></div>`
- The directive has that modifier. E.g. `<div v-for.bbb></div>`
- The directive does not have that attribute value. E.g. `<div v-for></div>`
- If the element which has the directive is a custom component, the component does not have `v-bind:key` directive. E.g. `<your-component v-for="item in list"></your-component>`
- The `v-bind:key` directive does not use the variables which are defined by the `v-for` directive. E.g. `<div v-for="x in list" :key="foo"></div>`

If the element which has the directive is a reserved element, this rule does not report it even if the element does not have `v-bind:key` directive because it's not fatal error. [require-v-for-key] rule reports it.

<eslint-code-block :rules="{'vue/valid-v-for': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-for="todo in todos"/>
  <MyComponent
    v-for="todo in todos"
    :key="todo.id"
  />
  <div
    v-for="todo in todos"
    :is="MyComponent"
    :key="todo.id"
  />

  <!-- ✗ BAD -->
  <div v-for/>
  <div v-for:aaa="todo in todos"/>
  <div v-for.bbb="todo in todos"/>
  <div
    v-for="todo in todos"
    is="MyComponent"
  />
  <MyComponent v-for="todo in todos"/>
  <MyComponent
    v-for="todo in todos"
    :key="foo"
  />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-for](https://eslint.vuejs.org/rules/valid-v-for.html)
