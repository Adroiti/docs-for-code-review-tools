Pattern: Unused selector in template

Issue: -

## Description

Disallows selectors that are defined but not used inside the component's template, ensuring all CSS is actually utilized.

## Examples

```vue
<template>
  <div>
    <div id="id_a"></div>
    <div class="class-b">
      <div class="class-c"></div>
    </div>
  </div>
</template>

<style scoped>
/* ✗ BAD */
ul {}
.class-unknown {}

/* ✓ GOOD */
#id_a {}
.class-b {}
.class-b > .class-c {}
</style>
```