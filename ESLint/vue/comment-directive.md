Pattern: comment directive

Issue: -

## Description

ESLint doesn't provide any API to enhance `eslint-disable` functionality and ESLint rules cannot affect other rules. But ESLint provides [processors API](https://eslint.org/docs/developer-guide/working-with-plugins#processors-in-plugins).

This rule sends all `eslint-disable`-like comments as errors to the post-process of the `.vue` file processor, then the post-process removes all `vue/comment-directive` errors and the reported errors in disabled areas.

<eslint-code-block :rules="{'vue/comment-directive': ['error'], 'vue/max-attributes-per-line': ['error']}">

```vue
<template>
  <!-- eslint-disable-next-line vue/max-attributes-per-line -->
  <div a="1" b="2" c="3" d="4">
  </div>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - comment-directive](https://eslint.vuejs.org/rules/comment-directive.html)
