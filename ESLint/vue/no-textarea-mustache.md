Pattern: Use of mustaches in `<textarea>`

Issue: -

## Description

This rule reports mustaches in `<textarea>`.

<eslint-code-block :rules="{'vue/no-textarea-mustache': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <textarea v-model="message" />

  <!-- ✗ BAD -->
  <textarea>{{ message }}</textarea>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-textarea-mustache](https://eslint.vuejs.org/rules/no-textarea-mustache.html)
