Pattern: Invalid casing for property name

Issue: -

## Description

This rule aims at enforcing the style for the `name` property casing for consistency purposes.

<eslint-code-block fix :rules="{'vue/name-property-casing': ['error']}">

```vue
<script>
  /* ✓ GOOD */
  export default {
    name: 'MyComponent'
  }
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/name-property-casing': ['error']}">

```vue
<script>
  /* ✗ BAD */
  export default {
    name: 'my-component'
  }
</script>
```

</eslint-code-block>

## Options

```json
{
  "vue/name-property-casing": ["error", "PascalCase" | "kebab-case"]
}
```

- `"PascalCase"` (default) ... Enforce the `name` property to Pascal case.
- `"kebab-case"` ... Enforce the `name` property to kebab case.

### `"kebab-case"`

<eslint-code-block fix :rules="{'vue/name-property-casing': ['error', 'kebab-case']}">

```vue
<script>
  /* ✓ GOOD */
  export default {
    name: 'my-component'
  }
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/name-property-casing': ['error', 'kebab-case']}">

```vue
<script>
  /* ✗ BAD */
  export default {
    name: 'MyComponent'
  }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - name-property-casing](https://eslint.vuejs.org/rules/name-property-casing.html)
