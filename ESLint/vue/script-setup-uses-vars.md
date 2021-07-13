Pattern: Prevent `<script setup>` variables used in `<template>` to be marked as unused

Issue: -

## Description

Without this rule this code triggers warning:

<eslint-code-block :rules="{'vue/script-setup-uses-vars': ['error'], 'no-unused-vars': ['error']}">

```vue
<script setup>
  // imported components are also directly usable in template
  import Foo from './Foo.vue'
  import { ref } from 'vue'

  // write Composition API code just like in a normal setup()
  // but no need to manually return everything
  const count = ref(0)
  const inc = () => {
    count.value++
  }
</script>

<template>
  <Foo :count="count" @click="inc" />
</template>
```

</eslint-code-block>

After turning on, `Foo` is being marked as used and `no-unused-vars` rule doesn't report an issue.

## When Not To Use It

If you are not using `<script setup>` or if you do not use the `no-unused-vars` rule then you can disable this rule.

## Further Reading

* [eslint-plugin-vue - script-setup-uses-vars](https://eslint.vuejs.org/rules/script-setup-uses-vars.html)
