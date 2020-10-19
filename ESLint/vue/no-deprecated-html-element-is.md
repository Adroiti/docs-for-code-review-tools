Pattern: Use of deprecated `is` attribute on HTML element

Issue: -

## Description

This rule reports deprecated the `is` attribute on HTML elements (removed in Vue.js v3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-html-element-is': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div />
  <component is="foo">

  <!-- ✗ BAD -->
  <div is="foo" />
  <div :is="foo" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-html-element-is](https://eslint.vuejs.org/rules/no-deprecated-html-element-is.html)
* [Migration Guide - Custom Elements Interop](https://v3.vuejs.org/guide/migration/custom-elements-interop.html#customized-built-in-elements)
* [Vue RFCs - 0027-custom-elements-interop](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0027-custom-elements-interop.md)
