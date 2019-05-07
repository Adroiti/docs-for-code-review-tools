Pattern: use v on exact

Issue: -

## Description

This rule enforce usage of `exact` modifier on `v-on` when there is another `v-on` with modifier.

<eslint-code-block :rules="{'vue/use-v-on-exact': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button @click="foo" :click="foo"></button>
  <button v-on:click.exact="foo" v-on:click.ctrl="foo"></button>

  <!-- ✗ BAD -->
  <button v-on:click="foo" v-on:click.ctrl="foo"></button>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/use-v-on-exact": ["error"]
}
```.

## Further Reading

* [eslint-plugin-vue - use-v-on-exact](https://eslint.vuejs.org/rules/use-v-on-exact.html)
