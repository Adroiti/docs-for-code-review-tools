Pattern: Adding an argument to `v-model` used in custom component

Issue: -

## Description

This rule reports `v-model` directives in the following cases:

- The directive used on component has an argument. E.g. `<MyComponent v-model:aaa="foo" />`

<eslint-code-block :rules="{'vue/no-v-model-argument': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-model="foo" />


  <!-- ✗ BAD -->
  <MyComponent v-model:aaa="foo" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-v-model-argument](https://eslint.vuejs.org/rules/no-v-model-argument.html)
