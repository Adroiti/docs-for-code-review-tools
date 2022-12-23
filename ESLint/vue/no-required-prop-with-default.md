Pattern: Non-optional prop with default value

Issue: -

## Description

If a prop is declared with a default value, whether it is required or not, we can always skip it in actual use. In that situation, the default value would be applied. So, a required prop with a default value is essentially the same as an optional prop. This rule enforces all props with default values to be optional.

```vue
<script setup lang="ts">
  /* ✓ GOOD */
  const props = withDefaults(
    defineProps<{
      name?: string | number
      age?: number
    }>(),
    {
      name: "Foo",
    }
  );

  /* ✗ BAD */
  const props = withDefaults(
    defineProps<{
      name: string | number
      age?: number
    }>(),
    {
      name: "Foo",
    }
  );
</script>
```

## Further Reading

* [eslint-plugin-vue - no-required-prop-with-default ](https://eslint.vuejs.org/rules/no-required-prop-with-default.html)
