Pattern: Inconsistent `v-on` event handler style

Issue: -

## Description

This rule aims to enforce a consistent style in v-on event handlers.

```vue
<template>
  <!-- ✓ GOOD -->
  <button v-on:click="handler" />

  <!-- ✗ BAD -->
  <button v-on:click="handler()" />
  <button v-on:click="() => handler()" />
</template>
```

## Further Reading

* [eslint-plugin-vue - v-on-handler-style](https://eslint.vuejs.org/rules/v-on-handler-style.html)
