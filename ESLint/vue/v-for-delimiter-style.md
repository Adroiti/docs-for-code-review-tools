Pattern: Inconsistent `v-for` delimiter style

Issue: -

## Description

This rule enforces which delimiter (`in` or `of`) should be used in `v-for` directives.

<eslint-code-block fix :rules="{'vue/v-for-delimiter-style': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-for="x in xs" />

  <!-- ✗ BAD -->
  <div v-for="x of xs" />
</template>
```

</eslint-code-block>

## Options
Default is set to `in`.

```json
{
  "vue/v-for-delimiter-style": ["error", "in" | "of"]
}
```

- `"in"` (default) ... requires using `in`.
- `"of"` ... requires using `of`.

### `"of"`

<eslint-code-block fix :rules="{'vue/v-for-delimiter-style': ['error', 'of']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-for="x of xs" />

  <!-- ✗ BAD -->
  <div v-for="x in xs" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - v-for-delimiter-style](https://eslint.vuejs.org/rules/v-for-delimiter-style.html)
* [Guide - List Rendering](https://v3.vuejs.org/guide/list.html)
