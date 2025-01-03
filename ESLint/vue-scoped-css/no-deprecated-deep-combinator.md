Pattern: Deprecated deep combinator usage

Issue: -

## Description

Disallows use of deprecated deep combinators (`>>>` and `/deep/`) in favor of modern syntax.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.a >>> .b {}
.a /deep/ .b {}

/* ✓ GOOD */
.a ::v-deep(.b) {} /* Vue.js 3.x */
.a ::v-deep .b {} /* Vue.js 2.x */
</style>
```