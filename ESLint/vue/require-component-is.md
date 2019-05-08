Pattern: Missing `v-bind:is` for `<component>` element

Issue: -

## Description

This rule reports the `<component>` elements which do not have `v-bind:is` attributes.


<eslint-code-block :rules="{'vue/require-component-is': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <component :is="type"/>
  <component v-bind:is="type"/>

  <!-- ✗ BAD -->
  <component/>
  <component is="type"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-component-is](https://eslint.vuejs.org/rules/require-component-is.html)
