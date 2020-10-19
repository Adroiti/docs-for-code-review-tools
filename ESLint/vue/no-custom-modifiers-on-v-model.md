Pattern: Use of custom modifier on `v-model`

Issue: -

## Description

This rule reports `v-model` directives in the following cases:

- The directive used on the component has custom modifiers. E.g. `<MyComponent v-model.aaa="foo" />`

<eslint-code-block :rules="{'vue/no-custom-modifiers-on-v-model': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-model="foo" />
  <MyComponent v-model.trim="foo" />
  <MyComponent v-model.lazy="foo" />
  <MyComponent v-model.number="foo" />


  <!-- ✗ BAD -->
  <MyComponent v-model.aaa="foo" />
  <MyComponent v-model.aaa.bbb="foo" />

</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-custom-modifiers-on-v-model](https://eslint.vuejs.org/rules/no-custom-modifiers-on-v-model.html)
