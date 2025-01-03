Pattern: Unused CSS selector

Issue: - 

## Description

Disallows CSS selectors that are defined but not used in the component template to keep styles clean and maintainable.

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
.class-unknown {}
#id_unknown {}

/* ✓ GOOD */
#id_a {}
.class-b {}
.class-b > .class-c {}
</style>
```