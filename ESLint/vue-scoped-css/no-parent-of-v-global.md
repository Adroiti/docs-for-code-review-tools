Pattern: Parent selector for `::v-global` pseudo-element

Issue: -

## Description

Disallows parent selector for `::v-global` pseudo-element to avoid CSS selector confusion and maintain clear scope boundaries.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.bar ::v-global(.foo) {}

/* ✓ GOOD */
::v-global(.foo) {}
</style>
```