Pattern: Inconsistent slotted selector style

Issue: -

## Description

Enforces consistent usage of either `:slotted()` or `::v-slotted()` syntax for styling slot content.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.foo ::v-slotted(.bar) {}

/* ✓ GOOD */
.foo :slotted(.bar) {}
</style>
```