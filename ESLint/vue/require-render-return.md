Pattern: require render return

Issue: -

## Description

This rule aims to enforce render function to always return value

<eslint-code-block :rules="{'vue/require-render-return': ['error']}">

```vue
<script>
export default {
  /* ✓ GOOD */
  render (h) {
    return h('div', 'hello')
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/require-render-return': ['error']}">

```vue
<script>
export default {
  /* ✗ BAD */
  render (h) {
    if (foo) {
      return h('div', 'hello')
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-render-return](https://eslint.vuejs.org/rules/require-render-return.html)
