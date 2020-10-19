Pattern: Use of extra parentheses

Issue: -

## Description

This rule restricts the use of parentheses to only where they are necessary. This rule extends the core `no-extra-parens` rule and applies it to the `<template>`. This rule also checks some Vue.js syntax.

<eslint-code-block fix :rules="{'vue/no-extra-parens': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div :class="foo + bar" />
  {{ foo + bar }}
  {{ foo + bar | filter }}
  <!-- ✗ BAD -->
  <div :class="(foo + bar)" />
  {{ (foo + bar) }}
  {{ (foo + bar) | filter }}
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-extra-parens](https://eslint.vuejs.org/rules/no-extra-parens.html)
