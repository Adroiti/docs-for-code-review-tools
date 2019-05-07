Pattern: no confusing v for v if

Issue: -

## Description

This rule reports the elements which have both `v-for` and `v-if` directives in the following cases:

- The `v-if` directive does not use the reference which is to the variables which are defined by the `v-for` directives.

In that case, the `v-if` should be written on the wrapper element.

<eslint-code-block :rules="{'vue/no-confusing-v-for-v-if': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <TodoItem
    v-for="todo in todos"
    v-if="todo.shown"
    :todo="todo"
  />
  <ul v-if="shown">
    <TodoItem
      v-for="todo in todos"
      :todo="todo"
    />
  </ul>

  <!-- ✗ BAD -->
  <TodoItem
    v-if="complete"
    v-for="todo in todos"
    :todo="todo"
  />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-confusing-v-for-v-if](https://eslint.vuejs.org/rules/no-confusing-v-for-v-if.html)
