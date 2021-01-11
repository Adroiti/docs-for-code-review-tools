Pattern: Use of restricted prop

Issue: -

## Description

This rule allows you to specify props that you don't want to use in your application.

## Options

This rule takes a list of strings, where each string is a prop name or pattern to be restricted:

```json
{
  "vue/no-restricted-props": ["error", "value", "/^forbidden/"]
}
```

<eslint-code-block :rules="{'vue/no-restricted-props': ['error', 'value', '/^forbidden/']}">

```vue
<script>
export default {
  props: {
    /* ✗ BAD */
    value: String,
    forbiddenNum: Number,

    /* ✓ GOOD */
    foo: {},
    bar: {},
    arrowedBool: Boolean,
  }
}
</script>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-restricted-props': ['error', 'value', '/^forbidden/']}">

```vue
<script>
export default {
  props: [
    /* ✗ BAD */
    'value',
    'forbiddenNum',

    /* ✓ GOOD */
    'foo',
    'bar',
    'arrowedBool',
  ]
}
</script>
```

</eslint-code-block>

Alternatively, the rule also accepts objects.

```json
{
  "vue/no-restricted-props": ["error",
    {
      "name": "value",
      "message": "If you intend a prop for v-model, it should be 'modelValue' in Vue 3.",
      "suggest": "modelValue"
    },
  ]
}
```

The following properties can be specified for the object.

- `name` ... Specify the prop name or pattern.
- `message` ... Specify an optional custom message.
- `suggest` ... Specify an optional name to suggest changes.

<eslint-code-block :rules="{'vue/no-restricted-props': ['error', { name: 'value', message: 'If you intend a prop for v-model, it should be \'modelValue\' in Vue 3.', suggest: 'modelValue'}]}">

```vue
<script>
export default {
  props: [
    /* ✗ BAD */
    'value',
  ]
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-restricted-props](https://eslint.vuejs.org/rules/no-restricted-props.html)
