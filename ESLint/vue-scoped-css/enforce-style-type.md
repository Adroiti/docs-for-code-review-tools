Pattern: Missing style type

Issue: -

## Description

Enforces that `<style>` tags must have a type specified - either plain, scoped, or module - to maintain consistent styling approach.

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

<!-- ✓ GOOD -->
<style module>
</style>
```