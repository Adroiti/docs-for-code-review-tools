Pattern: Use of `v-text`/`v-html` on component

Issue: -

## Description

If you use `v-text`/`v-html` on a component, it will overwrite the component's content and may break the component.

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-text="content"></div>
  <div v-html="html"></div>
  <MyComponent>{{content}}</MyComponent>

  <!-- ✗ BAD -->
  <MyComponent v-text="content"></MyComponent>
  <MyComponent v-html="html"></MyComponent>
</template>
```

## Further Reading

* [eslint-plugin-vue - no-v-text-v-html-on-component](https://eslint.vuejs.org/rules/no-v-text-v-html-on-component.html)
