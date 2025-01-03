Pattern: Invalid CSS syntax

Issue: -

## Description

Disallows CSS parsing errors in `<style>` tags to ensure valid stylesheet syntax.

## Examples

```vue
<style scoped>
/* ✗ BAD */
.item {

/* ✓ GOOD */
.item {
  color: blue;
}
</style>
```