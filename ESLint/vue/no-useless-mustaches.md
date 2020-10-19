Pattern: Use of unnecessary mustache

Issue: -

## Description

This rule reports mustache interpolation with a string literal value.  
The mustache interpolation with a string literal value can be changed to a static contents.

<eslint-code-block fix :rules="{'vue/no-useless-mustaches': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  Lorem ipsum
  {{ foo }}

  <!-- ✗ BAD -->
  {{ 'Lorem ipsum' }}
  {{ "Lorem ipsum" }}
  {{ `Lorem ipsum` }}
</template>
```

</eslint-code-block>

## Options

```js
{
  "vue/no-useless-mustaches": ["error", {
    "ignoreIncludesComment": false,
    "ignoreStringEscape": false
  }]
}
```

- `ignoreIncludesComment` ... If `true`, do not report expressions containing comments. default `false`.
- `ignoreStringEscape` ... If `true`, do not report string literals with useful escapes. default `false`.

### `"ignoreIncludesComment": true`

<eslint-code-block fix :rules="{'vue/no-useless-mustaches': ['error', {ignoreIncludesComment: true}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  {{ 'Lorem ipsum'/* comment */ }}

  <!-- ✗ BAD -->
  {{ 'Lorem ipsum' }}
</template>
```

</eslint-code-block>

### `"ignoreStringEscape": true`

<eslint-code-block fix :rules="{'vue/no-useless-mustaches': ['error', {ignoreStringEscape: true}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  {{ 'Lorem \n ipsum' }}
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-useless-mustaches](https://eslint.vuejs.org/rules/no-useless-mustaches.html)
