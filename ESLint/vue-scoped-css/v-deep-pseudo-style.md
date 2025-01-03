Pattern: Inconsistent deep selector style

Issue: -

## Description

Enforces consistent usage of either `:deep()` or `::v-deep()` syntax for targeting nested components.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.foo ::v-deep(.bar) {}

/* ✓ GOOD */
.foo :deep(.bar) {}
</style>
```