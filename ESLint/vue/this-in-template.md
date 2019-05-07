Pattern: this in template

Issue: -

## Description

This rule aims at preventing usage of `this` in Vue templates.

<eslint-code-block :rules="{'vue/this-in-template': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <a :href="url">
    {{ text }}
  </a>
  
  <!-- ✗ BAD -->
  <a :href="this.url">
    {{ this.text }}
  </a>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/this-in-template": ["error", "always" | "never"]
}
```
- `"always"` ... Always use `this` while accessing properties from Vue.
- `"never"` (default) ... Never use `this` keyword in expressions.

### `"always"`

<eslint-code-block :rules="{'vue/this-in-template': ['error', 'always']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <a :href="this.url">
    {{ this.text }}
  </a>
  
  <!-- ✗ BAD -->
  <a :href="url">
    {{ text }}
  </a>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - this-in-template](https://eslint.vuejs.org/rules/this-in-template.html)
