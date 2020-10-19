Pattern: Deprecated data object declaration

Issue: -

## Description

This rule reports use of deprecated object declaration on `data` property (in Vue.js 3.0.0+).
The different from `vue/no-shared-component-data` is the root instance being also disallowed.

<eslint-code-block fix :rules="{'vue/no-deprecated-data-object-declaration': ['error']}" language="javascript" filename="example.js">

```js
createApp({
  /* ✗ BAD */
  data: {
    foo: null
  }
}).mount('#app')

createApp({
  /* ✓ GOOD */
  data () {
    return {
      foo: null
    }
  }
}).mount('#app')
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/no-deprecated-data-object-declaration': ['error']}">

```vue
<script>
export default {
  /* ✗ BAD */
  data: {
    foo: null
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/no-deprecated-data-object-declaration': ['error']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  data () {
    return {
      foo: null
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-data-object-declaration](https://eslint.vuejs.org/rules/no-deprecated-data-object-declaration.html)
