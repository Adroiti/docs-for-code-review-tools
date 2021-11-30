Pattern: Missing multi-word component name

Issue: -

## Description

This rule require component names to be always multi-word, except for root `App`
components, and built-in components provided by Vue, such as `<transition>` or
`<component>`. This prevents conflicts with existing and future HTML elements,
since all HTML elements are a single word.

<eslint-code-block filename="src/TodoItem.js" language="javascript" :rules="{'vue/multi-word-component-names': ['error']}">

```js
/* ✓ GOOD */
Vue.component('todo-item', {
  // ...
})

/* ✗ BAD */
Vue.component('Todo', {
  // ...
})
```

</eslint-code-block>

<eslint-code-block filename="src/TodoItem.js" :rules="{'vue/multi-word-component-names': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'TodoItem',
  // ...
}
</script>
```

</eslint-code-block>

<eslint-code-block filename="src/Todo.vue" :rules="{'vue/multi-word-component-names': ['error']}">

```vue
<script>
/* ✗ BAD */
export default {
  name: 'Todo',
  // ...
}
</script>
```

</eslint-code-block>

<eslint-code-block filename="src/Todo.vue" :rules="{'vue/multi-word-component-names': ['error']}">

```vue
<!-- filename: Todo.vue -->
<script>
/* ✗ BAD */
export default {
  // ...
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/multi-word-component-names": ["error", {
    "ignores": []
  }]
}
```

- `ignores` (`string[]`) ... The component names to ignore. Sets the component name to allow.

### `ignores: ["Todo"]`

<eslint-code-block :rules="{'vue/multi-word-component-names': ['error', {ignores: ['Todo']}]}">

```vue
<script>
export default {
  /* ✓ GOOD */
  name: 'Todo'
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/multi-word-component-names': ['error', {ignores: ['Todo']}]}">

```vue
<script>
export default {
  /* ✗ BAD */
  name: 'Item'
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - multi-word-component-names](https://eslint.vuejs.org/rules/multi-word-component-names.html)
* [Style guide - Multi-word component names](https://v3.vuejs.org/style-guide/#multi-word-component-names-essential)
