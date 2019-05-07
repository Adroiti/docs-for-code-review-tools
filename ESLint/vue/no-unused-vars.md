Pattern: no unused vars

Issue: -

## Description

This rule report variable definitions of v-for directives or scope attributes if those are not used.

<eslint-code-block :rules="{'vue/no-unused-vars': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <ol v-for="i in 5">
    <li>{{ i }}</li>
  </ol>

  <!-- ✗ BAD -->
  <ol v-for="i in 5">
    <li>item</li>
  </ol>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-unused-vars](https://eslint.vuejs.org/rules/no-unused-vars.html)
