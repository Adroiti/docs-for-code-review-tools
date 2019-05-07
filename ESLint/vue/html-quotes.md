Pattern: html quotes

Issue: -

## Description

This rule reports the quotes of attributes if it is different to configured quotes.

<eslint-code-block fix :rules="{'vue/html-quotes': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <img src="./logo.png">

  <!-- ✗ BAD -->
  <img src='./logo.png'>
  <img src=./logo.png>
</template>
```

</eslint-code-block>

## Options

Default is set to `double`.

```json
{
  "vue/html-quotes": ["error", "double" | "single"]
}
```

- `"double"` (default) ... requires double quotes.
- `"single"` ... requires single quotes.

### `"single"`

<eslint-code-block fix :rules="{'vue/html-quotes': ['error', 'single']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <img src='./logo.png'>

  <!-- ✗ BAD -->
  <img src="./logo.png">
  <img src=./logo.png>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-quotes](https://eslint.vuejs.org/rules/html-quotes.html)
