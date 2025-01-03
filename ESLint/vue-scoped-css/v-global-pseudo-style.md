Pattern: Inconsistent global selector style

Issue: -

## Description

Enforces consistent usage of either `:global()` or `::v-global()` syntax for global styles.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.foo ::v-global(.bar) {}

/* ✓ GOOD */
.foo :global(.bar) {}
</style>
```