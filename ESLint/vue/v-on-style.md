Pattern: v on style

Issue: -

## Description

This rule enforces `v-on` directive style which you should use shorthand or long form.

<eslint-code-block fix :rules="{'vue/v-on-style': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div @click="foo"/>

  <!-- ✗ BAD -->
  <div v-on:click="foo"/>
</template>
```

</eslint-code-block>

## Options
Default is set to `shorthand`.

```json
{
  "vue/v-on-style": ["error", "shorthand" | "longform"]
}
```

- `"shorthand"` (default) ... requires using shorthand.
- `"longform"` ... requires using long form.

### `"longform"`

<eslint-code-block fix :rules="{'vue/v-on-style': ['error', 'longform']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-on:click="foo"/>

  <!-- ✗ BAD -->
  <div @click="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - v-on-style](https://eslint.vuejs.org/rules/v-on-style.html)
