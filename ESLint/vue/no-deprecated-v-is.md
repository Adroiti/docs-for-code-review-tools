Pattern: Use of deprecated `v-is`

Issue: -

## Description

This rule reports deprecated `v-is` directive in Vue.js v3.1.0+.

Use [`is` attribute with `vue:` prefix](https://v3.vuejs.org/api/special-attributes.html#is) instead.

<eslint-code-block fix :rules="{'vue/no-deprecated-v-is': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div is="vue:MyComponent" />
  <component is="MyComponent" />
  
  <!-- ✗ BAD -->
  <div v-is="'MyComponent'" />
</template>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-deprecated-v-is](https://eslint.vuejs.org/rules/no-deprecated-v-is.html)
