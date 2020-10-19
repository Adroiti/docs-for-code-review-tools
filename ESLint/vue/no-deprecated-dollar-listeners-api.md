Pattern: Use of deprecated `$listeners`

Issue: -

## Description

This rule reports use of deprecated `$listeners`. (in Vue.js 3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-dollar-listeners-api': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <MyInput v-on="$listeners">
</template>
<script>
export default {
  computed: {
    listeners() {
      return {
        /* ✗ BAD */
        ...this.$listeners,
        input() { /* */ }
      }
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-dollar-listeners-api](https://eslint.vuejs.org/rules/no-deprecated-dollar-listeners-api.html)
