Pattern: Unused `@keyframes` animation

Issue: -

## Description

Disallows `@keyframes` animations that are not used within scoped CSS to avoid unused code.

## Examples

```vue
<style scoped>
.item {
    animation-name: slidein;
}

/* ✗ BAD */
@keyframes unused-animation {
}

/* ✓ GOOD */
@keyframes slidein {
}
</style>
```