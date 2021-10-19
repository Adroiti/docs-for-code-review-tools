Pattern: Use of restricted class

Issue: -

## Description

This rule lets you specify a list of classes that you don't want to allow in your templates

## Options

The simplest way to specify a list of forbidden classes is to pass it directly in the rule configuration.

```json
{
  "vue/no-restricted-class": ["error", "forbidden", "forbidden-two", "forbidden-three"]
}

```


```vue
<template>
  <!-- ✗ BAD -->
  <div class="forbidden" />
  <div :class="{forbidden: someBoolean}" />
  <div :class="`forbidden ${someString}`" />
  <div :class="'forbidden'" />
  <div :class="'forbidden ' + someString" />
  <div :class="[someString, 'forbidden']" />
  <!-- ✗ GOOD -->
  <div class="allowed-class" />
</template>

<script>
export default {
  props: {
    someBoolean: Boolean,
    someString: String,
  }
}
</script>

```

## Further Reading

* [eslint-plugin-vue - no-restricted-class](https://eslint.vuejs.org/rules/no-restricted-class.html)
