Pattern: Invalid attribute name

Issue: -

## Description

This rule detects invalid HTML attributes.

<eslint-code-block :rules="{'vue/valid-attribute-name': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <p foo.bar></p>
  <p foo-bar></p>
  <p _foo.bar></p>
  <p :foo-bar></p>

  <!-- ✗ BAD -->
  <p 0abc></p>
  <p -def></p>
  <p !ghi></p>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-attribute-name](https://eslint.vuejs.org/rules/valid-attribute-name.html)
