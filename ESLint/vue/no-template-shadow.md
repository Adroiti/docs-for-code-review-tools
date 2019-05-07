Pattern: no template shadow

Issue: -

## Description

This rule aims to eliminate shadowed variable declarations of v-for directives or scope attributes.

<eslint-code-block :rules="{'vue/no-template-shadow': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-for="i in 5"></div>
  <div v-for="j in 5"></div>

  <!-- ✗ BAD -->
  <div>
    <div v-for="k in 5">
      <div v-for="k in 10"></div>
      <div slot-scope="{ k }"></div>
    </div>
  </div>
  <div v-for="l in 5"></div>
</template>

<script>
  export default {
    data () {
      return {
        l: false
      }
    }
  }
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-template-shadow](https://eslint.vuejs.org/rules/no-template-shadow.html)
