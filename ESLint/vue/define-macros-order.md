Pattern: Wrong `defineProps`/`defineEmits` macro order

Issue: -

## Description

This rule reports the `defineProps` and `defineEmits` compiler macros when they are not the first statements in `<script setup>` (after any potential import statements or type definitions) or when they are not in the correct order.

## Options

```json
{
  "vue/define-macros-order": ["error", {
    "order": ["defineProps", "defineEmits"]
  }]
}
```

- `order` (`string[]`) ... The order of defineEmits and defineProps macros

### `{ "order": ["defineProps", "defineEmits"] }` (default)

<eslint-code-block fix :rules="{'vue/define-macros-order': ['error']}">

```vue
<!-- ✓ GOOD -->
<script setup>
defineProps(/* ... */)
defineEmits(/* ... */)
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/define-macros-order': ['error']}">

```vue
<!-- ✗ BAD -->
<script setup>
defineEmits(/* ... */)
defineProps(/* ... */)
</script>
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/define-macros-order': ['error']}">

```vue
<!-- ✗ BAD -->
<script setup>
const bar = ref()
defineProps(/* ... */)
defineEmits(/* ... */)
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - define-macros-order](https://eslint.vuejs.org/rules/define-macros-order.html)
