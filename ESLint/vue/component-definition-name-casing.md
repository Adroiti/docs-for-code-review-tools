Pattern: Invalid component definition name

Issue: -

## Description

This rule aims to warn the component definition names other than the configured casing.

## Options

Default casing is set to `PascalCase`.

```json
{
  "vue/component-definition-name-casing": ["error", "PascalCase" | "kebab-case"]
}
```

- `"PascalCase"` (default) ... enforce component definition names to pascal case.
- `"kebab-case"` ... enforce component definition names to kebab case.

### `"PascalCase" (default)

<eslint-code-block fix :rules="{'vue/component-definition-name-casing': ['error']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  name: 'MyComponent'
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/component-definition-name-casing': ['error']}">

```vue
<script>
export default {
  /* ✗ BAD */
  name: 'my-component'
}
</script>
```

</eslint-code-block>

<eslint-code-block fix language="javascript" filename="src/MyComponent.js" :rules="{'vue/component-definition-name-casing': ['error']}">

```js
/* ✓ GOOD */
Vue.component('MyComponent', {
  
})

/* ✗ BAD */
Vue.component('my-component', {
  
})
```

</eslint-code-block>

### `"kebab-case"

<eslint-code-block fix :rules="{'vue/component-definition-name-casing': ['error', 'kebab-case']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  name: 'my-component'
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/component-definition-name-casing': ['error', 'kebab-case']}">

```vue
<script>
export default {
  /* ✗ BAD */
  name: 'MyComponent'
}
</script>
```

</eslint-code-block>

<eslint-code-block fix language="javascript" filename="src/MyComponent.js" :rules="{'vue/component-definition-name-casing': ['error', 'kebab-case']}">

```js
/* ✓ GOOD */
Vue.component('my-component', {
  
})

/* ✗ BAD */
Vue.component('MyComponent', {
  
})
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - component-definition-name-casing](https://eslint.vuejs.org/rules/component-definition-name-casing.html)
