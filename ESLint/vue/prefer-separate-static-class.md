Pattern: Use of static class name in dynamic class attribute

Issue: -

## Description

This rule reports static class names in dynamic class attributes.

<eslint-code-block fix :rules="{'vue/prefer-separate-static-class': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div :class="'static-class'" />
  <div :class="{'static-class': true, 'dynamic-class': foo}" />
  <div :class="['static-class', dynamicClass]" />

  <!-- ✓ GOOD -->
  <div class="static-class" />
  <div class="static-class" :class="{'dynamic-class': foo}" />
  <div class="static-class" :class="[dynamicClass]" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - prefer-separate-static-class](https://eslint.vuejs.org/rules/prefer-separate-static-class.html)
