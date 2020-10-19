Pattern: Duplicate attribute inheritance

Issue: -

## Description

This rule aims to prevent duplicated attribute inheritance. This rule to warn to apply `inheritAttrs: false` when it detects `v-bind="$attrs"` being used.

<eslint-code-block :rules="{'vue/no-duplicate-attr-inheritance': ['error']}">

```vue
<template>
  <MyInput v-bind="$attrs" />
</template>
<script>
export default {
  /* ✓ GOOD */
  inheritAttrs: false
}
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-duplicate-attr-inheritance': ['error']}">

```vue
<template>
  <MyInput v-bind="$attrs" />
</template>
<script>
export default {
  /* ✗ BAD */
  // inheritAttrs: true (default)
}
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-duplicate-attr-inheritance](https://eslint.vuejs.org/rules/no-duplicate-attr-inheritance.html)
* [API - inheritAttrs](https://v3.vuejs.org/api/options-misc.html#inheritattrs)
