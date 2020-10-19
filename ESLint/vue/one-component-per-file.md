Pattern: More than one component per file

Issue: -

## Description

This rule checks if there is only one component per file.

<eslint-code-block filename="a.js" language="javascript" :rules="{'vue/one-component-per-file': ['error']}">

```js
/* ✗ BAD */

Vue.component('TodoList', {
  // ...
})

Vue.component('TodoItem', {
  // ...
})
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/one-component-per-file': ['error']}">

```vue
<script>
/* ✓ GOOD */
export default {
  name: 'my-component'
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - one-component-per-file](https://eslint.vuejs.org/rules/one-component-per-file.html)
* [Style guide - Component files](https://v3.vuejs.org/style-guide/#component-files-strongly-recommended)
