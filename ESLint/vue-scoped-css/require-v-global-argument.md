Pattern: Missing `::v-global()` argument

Issue: -

## Description

Requires that a selector argument be passed to `::v-global()` pseudo-element for explicit global style targeting.

## Examples

```vue
<style scoped>
/* ✗ BAD */
::v-global() {}
::v-global {}

/* ✓ GOOD */
::v-global(.foo .bar) {}
</style>
```