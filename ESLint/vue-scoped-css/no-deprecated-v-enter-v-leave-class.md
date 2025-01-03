Pattern: Deprecated transition class name

Issue: -

## Description

Disallows use of deprecated `v-enter` and `v-leave` transition class names in favor of `v-enter-from` and `v-leave-from`.

## Examples

```vue
<template>
  <Transition><div v-if="foo"/></Transition>
</template>

<style scoped>
/* ✗ BAD */
.v-enter {}
.v-leave {}

/* ✓ GOOD */
.v-enter-from {}
.v-leave-from {}
</style>
```