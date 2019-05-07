Pattern: no multi spaces

Issue: -

## Description

This rule aims at removing multiple spaces in tags, which are not used for indentation.

<eslint-code-block fix :rules="{'vue/no-multi-spaces': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div
    class="foo"
    :style="bar" />
  <i
    :class="{
      'fa-angle-up' : isExpanded,
      'fa-angle-down' : !isExpanded,
    }"
  />

  <!-- ✗ BAD -->
  <div     class="foo"
    :style =  "bar"         />
  <i
    :class="{
      'fa-angle-up'   : isExpanded,
      'fa-angle-down' : !isExpanded,
    }"
  />
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-multi-spaces": ["error", {
    "ignoreProperties": false
  }]
}
```

- `ignoreProperties` ... whether or not objects' properties should be ignored. default `false`

### `"ignoreProperties": true`

<eslint-code-block fix :rules="{'vue/no-multi-spaces': ['error', { 'ignoreProperties': true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <i
    :class="{
      'fa-angle-up'   : isExpanded,
      'fa-angle-down' : !isExpanded,
    }"
  />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-multi-spaces](https://eslint.vuejs.org/rules/no-multi-spaces.html)
