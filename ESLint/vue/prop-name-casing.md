Pattern: prop name casing

Issue: -

## Description

This rule enforce proper casing of props in vue components(camelCase).

<eslint-code-block fix :rules="{'vue/prop-name-casing': ['error']}">

```vue
<script>
export default {
  props: {
    /* ✓ GOOD */
    greetingText: String,

    /* ✗ BAD */
    'greeting-text': String,
    greeting_text: String
  }
}
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/prop-name-casing": ["error", "camelCase" | "snake_case"]
}
```

- `"camelCase"` (default) ... Enforce property names in `props` to camel case.
- `"snake_case"` ... Enforce property names in `props` to snake case.

### `"snake_case"`

<eslint-code-block fix :rules="{'vue/prop-name-casing': ['error', 'snake_case']}">

```vue
<script>
export default {
  props: {
    /* ✓ GOOD */
    greeting_text: String,

    /* ✗ BAD */
    'greeting-text': String,
    greetingText: String
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - prop-name-casing](https://eslint.vuejs.org/rules/prop-name-casing.html)
