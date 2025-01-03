Pattern: Missing `::v-slotted()` argument

Issue: -

## Description

Requires that a selector argument be passed to `::v-slotted()` pseudo-element when styling slotted content.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.baz .qux ::v-slotted() {}
.baz .qux ::v-slotted {}

/* ✓ GOOD */
.baz .qux ::v-slotted(.foo .bar) {}
</style>
```