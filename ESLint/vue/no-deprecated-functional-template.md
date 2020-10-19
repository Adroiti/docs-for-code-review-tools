Pattern: Use of deprecated the `functional` template

Issue: -

## Description

This rule reports deprecated the `functional` template (in Vue.js 3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-functional-template': ['error']}">

```vue
<!-- ✗ BAD -->
<template functional>
  <!-- ... -->
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-functional-template](https://eslint.vuejs.org/rules/no-deprecated-functional-template.html)
* [Migration Guide - Functional Components](https://v3.vuejs.org/guide/migration/functional-components.html)
* [Vue RFCs - 0007-functional-async-api-change](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0007-functional-async-api-change.md)
* [Guide - Functional Components](https://vuejs.org/v2/guide/render-function.html#Functional-Components)

