Pattern: Space around equal sign in attribute

Issue: -

## Description

This rule disallow spaces around equal signs in attribute.

<eslint-code-block fix :rules="{'vue/no-spaces-around-equal-signs-in-attribute': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div class = "item"></div>
  <!-- ✓ GOOD -->
  <div class="item"></div>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-spaces-around-equal-signs-in-attribute": ["error"]
}
```.

## Further Reading

* [eslint-plugin-vue - no-spaces-around-equal-signs-in-attribute](https://eslint.vuejs.org/rules/no-spaces-around-equal-signs-in-attribute.html)
