Pattern: Wrong static class name order

Issue: -

## Description

This rule aims to enforce the order of static class names.

## Examples

```vue
<template>
  <!-- ✓ GOOD -->
  <div class="a b"></div>

  <!-- ✗ BAD -->
  <div class="b a"></div>
</template>
```

## Further Reading

* [eslint-plugin-vue - static-class-names-order](https://eslint.vuejs.org/rules/static-class-names-order.html)
