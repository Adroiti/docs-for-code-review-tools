Pattern: Use of button without explicit type

Issue: -

## Description

Forgetting the type attribute on a button defaults it to being a submit type. This is nearly never what is intended, especially in your average one-page application.

```vue
<template>
  <!-- ✓ GOOD -->
  <button type="button">Hello World</button>
  <button type="submit">Hello World</button>
  <button type="reset">Hello World</button>

  <!-- ✗ BAD -->
  <button>Hello World</button>
  <button type="">Hello World</button>
  <button type="foo">Hello World</button>
</template>
```

## Further Reading

* [eslint-plugin-vue - html-button-has-type](https://eslint.vuejs.org/rules/html-button-has-type.html)
