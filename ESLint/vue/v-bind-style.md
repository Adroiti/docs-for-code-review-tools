Pattern: Malformed `v-bind` directive

Issue: -

## Description

This rule enforces `v-bind` directive style which you should use shorthand or long form.

<eslint-code-block fix :rules="{'vue/v-bind-style': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div :foo="bar"/>

  <!-- ✗ BAD -->
  <div v-bind:foo="bar"/>
</template>
```

</eslint-code-block>

## Options
Default is set to `shorthand`.

```json
{
  "vue/v-bind-style": ["error", "shorthand" | "longform"]
}
```

- `"shorthand"` (default) ... requires using shorthand.
- `"longform"` ... requires using long form.

### `"longform"`

<eslint-code-block fix :rules="{'vue/v-bind-style': ['error', 'longform']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-bind:foo="bar"/>

  <!-- ✗ BAD -->
  <div :foo="bar"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - v-bind-style](https://eslint.vuejs.org/rules/v-bind-style.html)
