Pattern: Disallowed name in prop

Issue: -

## Description

Disallow reserved names to be used in props.

<eslint-code-block :rules="{'vue/no-reserved-props': ['error']}">

```vue
<script>
export default {
  props: {
    /* ✗ BAD */
    ref: String,
    key: String,
    /* ✓ GOOD */
    foo: String,
    bar: String,
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-reserved-props": ["error", {
    "vueVersion": 3, // or 2
  }]
}
```

- `vueVersion` (`2 | 3`) ... Specify the version of Vue you are using. Default is `3`.


## Further Reading

* [eslint-plugin-vue - no-reserved-props](https://eslint.vuejs.org/rules/no-reserved-props.html)
