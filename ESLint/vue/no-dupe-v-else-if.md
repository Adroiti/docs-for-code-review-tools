Pattern: Duplicate condition in `v-if`/`v-else-if` chain

Issue: -

## Description

This rule disallows duplicate conditions in the same `v-if`/`v-else-if` chain.

<eslint-code-block :rules="{'vue/no-dupe-v-else-if': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div v-if="isSomething(x)" />
  <div v-else-if="isSomething(x)" />

  <div v-if="a" />
  <div v-else-if="b" />
  <div v-else-if="c && d" />
  <div v-else-if="c && d" />

  <div v-if="n === 1" />
  <div v-else-if="n === 2" />
  <div v-else-if="n === 3" />
  <div v-else-if="n === 2" />
  <div v-else-if="n === 5" />

  <!-- ✓ GOOD -->
  <div v-if="isSomething(x)" />
  <div v-else-if="isSomethingElse(x)" />

  <div v-if="a" />
  <div v-else-if="b" />
  <div v-else-if="c && d" />
  <div v-else-if="c && e" />

  <div v-if="n === 1" />
  <div v-else-if="n === 2" />
  <div v-else-if="n === 3" />
  <div v-else-if="n === 4" />
  <div v-else-if="n === 5" />
</template>
```

</eslint-code-block>

This rule can also detect some cases where the conditions are not identical, but the branch can never execute due to the logic of `||` and `&&` operators.

<eslint-code-block :rules="{'vue/no-dupe-v-else-if': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div v-if="a || b" />
  <div v-else-if="a" />

  <div v-if="a" />
  <div v-else-if="b" />
  <div v-else-if="a || b" />

  <div v-if="a" />
  <div v-else-if="a && b" />

  <div v-if="a && b" />
  <div v-else-if="a && b && c" />

  <div v-if="a || b" />
  <div v-else-if="b && c" />

  <div v-if="a" />
  <div v-else-if="b && c" />
  <div v-else-if="d && (c && e && b || a)" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-dupe-v-else-if](https://eslint.vuejs.org/rules/no-dupe-v-else-if.html)
