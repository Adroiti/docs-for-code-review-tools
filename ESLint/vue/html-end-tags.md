Pattern: html end tags

Issue: -

## Description

This rule aims to disallow lacking end tags.

<eslint-code-block fix :rules="{'vue/html-end-tags': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div></div>
  <p></p>
  <p></p>
  <input>
  <br>

  <!-- ✗ BAD -->
  <div>
  <p>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - html-end-tags](https://eslint.vuejs.org/rules/html-end-tags.html)
