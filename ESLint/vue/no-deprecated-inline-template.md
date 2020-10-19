Pattern: Use of deprecated `inline-template` attribute

Issue: -

## Description

This rule reports deprecated `inline-template` attributes (removed in Vue.js v3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-inline-template': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <my-comnponent />

  <!-- ✗ BAD -->
  <my-component inline-template>
    <div>
      <p>These are compiled as the component's own template.</p>
      <p>Not parent's transclusion content.</p>
    </div>
  </my-component>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-inline-template](https://eslint.vuejs.org/rules/no-deprecated-inline-template.html)
* [Migration Guide - Inline Template Attribute](https://v3.vuejs.org/guide/migration/inline-template-attribute.html)
* [Vue RFCs - 0016-remove-inline-templates](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0016-remove-inline-templates.md)
