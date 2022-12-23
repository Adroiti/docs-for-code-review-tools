Pattern: Missing newline between operands of ternary expression

Issue: -

## Description

Enforce newlines between operands of ternary expressions in `<template>`.

This rule is the same rule as core multiline-ternary rule but it applies to the expressions in `<template>` and `<style>`.

```vue
<template>
  <div>
    <!-- ✓ GOOD -->
    <div :class="isEnabled
      ? 'check'
      : 'stop'" />

    <!-- ✗ BAD -->
    <div :class="isEnabled ? 'check' : 'stop'" />
  </div>
</template>

<style>
div {
  /* ✓ GOOD */
  color: v-bind('myFlag
    ? foo
    : bar');

  /* ✗ BAD */
  color: v-bind('myFlag ? foo : bar');
}
</style>
```

## Further Reading

* [eslint-plugin-vue - multiline-ternary](https://eslint.vuejs.org/rules/multiline-ternary.html#vue-multiline-ternary)
