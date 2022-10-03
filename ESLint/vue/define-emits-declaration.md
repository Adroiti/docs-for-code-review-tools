Pattern: Inconsistent `defineEmits` style

Issue: -

## Description

This rule enforces `defineEmits` typing style which you should use `type-based` or `runtime` declaration.

This rule only works in setup script and `lang="ts"`.

```vue
<script setup lang="ts">
/* ✓ GOOD */
const emit = defineEmits<{
  (e: 'change', id: number): void
  (e: 'update', value: string): void
}>()

/* ✗ BAD */
const emit = defineEmits({
  change: (id) => typeof id == 'number',
  update: (value) => typeof value == 'string'
})

/* ✗ BAD */
const emit = defineEmits(['change', 'update'])
</script>
```

## Further Reading

* [eslint-plugin-vue - define-emits-declaration](https://eslint.vuejs.org/rules/define-emits-declaration.html)
