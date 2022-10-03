Pattern: Inconsistent `defineProps` style

Issue: -

## Description

This rule enforces `defineProps ` typing style which you should use `type-based` or `runtime` declaration.

This rule only works in setup script and `lang="ts"`.

```vue
<script setup lang="ts">
/* ✓ GOOD */
const props = defineProps<{
  kind: string,
  options: { title: string }
}>()

/* ✗ BAD */
const props = defineProps({
  kind: { type: String },
  options: { type: Object as PropType<{ title: string }> }
})
</script>
```

## Further Reading

* [eslint-plugin-vue - define-props-declaration](https://eslint.vuejs.org/rules/define-emits-declaration.html)
