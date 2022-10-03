Pattern: Malformed newline between sibling HTML tags

Issue: -

## Description

This rule requires or disallows newlines between sibling HTML tags.

```vue
<template>
  <div>
    <!-- ✓ GOOD: -->
    <div></div>

    <div>
    </div>
    
    <div />

    <div />
    <!-- ✗ BAD: -->
    <div></div>
    <div>
    </div>
    <div /><div />
  </div>
</template>
```

## Further Reading

* [eslint-plugin-vue - padding-line-between-tags](https://eslint.vuejs.org/rules/padding-line-between-tags.html)
