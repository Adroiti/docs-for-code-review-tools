Pattern: Missing toggle inside `<transition>`

Issue: -

## Description

This rule reports elements inside `<transition>` that do not control the display.

<eslint-code-block :rules="{'vue/require-toggle-inside-transition': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <transition><div v-if="show" /></transition>
  <transition><div v-show="show" /></transition>

  <!-- ✗ BAD -->
  <transition><div /></transition>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - require-toggle-inside-transition](https://eslint.vuejs.org/rules/require-toggle-inside-transition.html)
* [Vue RFCs - 0017-transition-as-root](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0017-transition-as-root.md)

