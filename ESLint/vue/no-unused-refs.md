Pattern: Unused `ref`

Issue: -

## Description

This rule reports refs that are defined using the `ref` attribute in `<template>` but are not used via `$refs`.

<eslint-code-block :rules="{'vue/no-unused-refs': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <input ref="foo" />

  <!-- ✗ BAD (`bar` is not used) -->
  <input ref="bar" />
</template>
<script>
export default {
  mounted() {
    this.$refs.foo.value = 'foo'
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-unused-refs](https://eslint.vuejs.org/rules/no-unused-refs.html)
