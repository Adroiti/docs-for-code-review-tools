Pattern: Use of `v-text` directive

Issue: -

## Description

Reports all uses of `v-text` directive.

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ foobar }}</div>

  <!-- ✗ BAD -->
  <div v-text="foobar"></div>
</template>
```

## Further Reading

* [eslint-plugin-vue - no-v-text](https://eslint.vuejs.org/rules/no-v-text.html)
