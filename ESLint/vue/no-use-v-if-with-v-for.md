Pattern: Use of `v-if` on the same element as `v-for`

Issue: -

## Description

This rule is aimed at preventing the use of `v-for` directives together with `v-if` directives on the same element.

There are two common cases where this can be tempting:
 * To filter items in a list (e.g. `v-for="user in users" v-if="user.isActive"`). In these cases, replace `users` with a new computed property that returns your filtered list (e.g. `activeUsers`).
 * To avoid rendering a list if it should be hidden (e.g. `v-for="user in users" v-if="shouldShowUsers"`). In these cases, move the `v-if` to a container element (e.g. `ul`, `ol`).

<eslint-code-block :rules="{'vue/no-use-v-if-with-v-for': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <ul v-if="complete">
    <TodoItem
      v-for="todo in todos"
      :todo="todo"
    />
  </ul>
  <TodoItem
    v-for="todo in shownTodos"
    :todo="todo"
  />

  <!-- ✗ BAD -->
  <TodoItem
    v-if="complete"
    v-for="todo in todos"
    :todo="todo"
  /><!-- ↑ In this case, the `v-if` should be written on the wrapper element. -->
  <TodoItem
    v-for="todo in todos"
    v-if="todo.shown"
    :todo="todo"
  /><!-- ↑ In this case, the `v-for` list variable should be replace with a computed property that returns your filtered list. -->
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-use-v-if-with-v-for": ["error", {
    "allowUsingIterationVar": false
  }]
}
```

- `allowUsingIterationVar` (`boolean`) ... Enables The `v-if` directive use the reference which is to the variables which are defined by the `v-for` directives. Default is `false`.

### `"allowUsingIterationVar": true`

<eslint-code-block :rules="{'vue/no-use-v-if-with-v-for': ['error', {allowUsingIterationVar: true}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <TodoItem
    v-for="todo in todos"
    v-if="todo.shown"
    :todo="todo"
  />

  <!-- ✗ BAD -->
  <TodoItem
    v-for="todo in todos"
    v-if="shown"
    :todo="todo"
  />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-use-v-if-with-v-for](https://eslint.vuejs.org/rules/no-use-v-if-with-v-for.html)
