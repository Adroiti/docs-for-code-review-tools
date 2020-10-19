Pattern: Use of `v-bind` with string literal value

Issue: -

## Description

This rule reports `v-bind` with a string literal value.  
The `v-bind` with a string literal value can be changed to a static attribute definition.

<eslint-code-block fix :rules="{'vue/no-useless-v-bind': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div foo="bar"/>
  <div :foo="bar"/>

  <!-- ✗ BAD -->
  <div v-bind:foo="'bar'"/>
  <div :foo="'bar'"/>
</template>
```

</eslint-code-block>

## Options

```js
{
  "vue/no-useless-v-bind": ["error", {
    "ignoreIncludesComment": false,
    "ignoreStringEscape": false
  }]
}
```

- `ignoreIncludesComment` ... If `true`, do not report expressions containing comments. default `false`.
- `ignoreStringEscape` ... If `true`, do not report string literals with useful escapes. default `false`.

### `"ignoreIncludesComment": true`

<eslint-code-block fix :rules="{'vue/no-useless-v-bind': ['error', {ignoreIncludesComment: true}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-bind:foo="'bar'/* comment */"/>

  <!-- ✗ BAD -->
  <div v-bind:foo="'bar'"/>
</template>
```

</eslint-code-block>

### `"ignoreStringEscape": true`

<eslint-code-block fix :rules="{'vue/no-useless-v-bind': ['error', {ignoreStringEscape: true}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-bind:foo="'bar\nbaz'"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-useless-v-bind](https://eslint.vuejs.org/rules/no-useless-v-bind.html)
