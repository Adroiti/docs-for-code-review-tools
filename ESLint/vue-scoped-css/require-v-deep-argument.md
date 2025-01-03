Pattern: Missing `::v-deep()` argument

Issue: -

## Description

Requires that a selector argument be passed to `::v-deep()` pseudo-element for clear scope targeting.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.baz .qux ::v-deep {}
.baz .qux ::v-deep() {}

/* ✓ GOOD */
.baz .qux ::v-deep(.foo .bar) {}
</style>
```