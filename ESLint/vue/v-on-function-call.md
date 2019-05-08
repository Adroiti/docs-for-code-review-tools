Pattern: Malformed parentheses for `v-on` directive

Issue: -

## Description

This rule aims to enforce to bind methods to `v-on` or call methods on `v-on` when without arguments.

<eslint-code-block fix :rules="{'vue/v-on-function-call': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button v-on:click="closeModal">
    Close
  </button>

  <!-- ✗ BAD -->
  <button v-on:click="closeModal()">
    Close
  </button>
</template>
```

</eslint-code-block>

## Options

Default is set to `never`.

```json
{
  "vue/v-on-function-call": ["error", "always"|"never"]
}
```

### `"always"` - Always use parentheses in `v-on` directives

<eslint-code-block fix :rules="{'vue/v-on-function-call': ['error', 'always']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button v-on:click="closeModal()">
    Close
  </button>

  <!-- ✗ BAD -->
  <button v-on:click="closeModal">
    Close
  </button>
</template>
```

</eslint-code-block>

### `"never"` - Never use parentheses in `v-on` directives for method calls without arguments


<eslint-code-block fix :rules="{'vue/v-on-function-call': ['error', 'never']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <button v-on:click="closeModal">
    Close
  </button>
  <button v-on:click="closeModal(arg)">
    Close
  </button>

  <!-- ✗ BAD -->
  <button v-on:click="closeModal()">
    Close
  </button>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - v-on-function-call](https://eslint.vuejs.org/rules/v-on-function-call.html)
