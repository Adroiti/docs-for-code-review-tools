Pattern: Missing scoped attribute

Issue: -

## Description

Enforces the `<style>` tags to have the `scoped` attribute. Note: This rule has been deprecated in favor of `enforce-style-type`.

## Examples

```vue
<template>
</template>

<!-- ✗ BAD -->
<style>
</style>

<!-- ✓ GOOD -->
<style scoped>
</style>
```