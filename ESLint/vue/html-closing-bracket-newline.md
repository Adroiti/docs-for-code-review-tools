Pattern: Malformed newline for HTML closing bracket

Issue: -

## Description

This rule aims to warn the right angle brackets which are at the location other than the configured location.

<eslint-code-block fix :rules="{'vue/html-closing-bracket-newline': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div id="foo" class="bar">
  <div
    id="foo"
    class="bar"
  >

  <!-- ✗ BAD -->
  <div id="foo" class="bar"
  >
  <div
    id="foo"
    class="bar">
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/html-closing-bracket-newline": ["error", {
    "singleline": "never",
    "multiline": "always"
  }]
}
```

- `singleline` ... the configuration for single-line elements. It's a single-line element if the element does not have attributes or the last attribute is on the same line as the opening bracket.
    - `"never"` (default) ... disallow line breaks before the closing bracket.
    - `"always"` ... require one line break before the closing bracket.
- `multiline` ... the configuration for multiline elements. It's a multiline element if the last attribute is not on the same line of the opening bracket.
    - `"never"` ... disallow line breaks before the closing bracket.
    - `"always"` (default) ... require one line break before the closing bracket.

Plus, you can use [`vue/html-indent`](./html-indent.md) rule to enforce indent-level of the closing brackets.

### `"multiline": "never"`

<eslint-code-block fix :rules="{'vue/html-closing-bracket-newline': ['error', { 'multiline': 'never' }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    id="foo"
    class="bar">

  <!-- ✗ BAD -->
  <div
    id="foo"
    class="bar"
  >
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-closing-bracket-newline](https://eslint.vuejs.org/rules/html-closing-bracket-newline.html)
