Pattern: Use of static inline style

Issue: -

## Description

This rule reports static inline `style` bindings and `style` attributes.
The styles reported in this rule mean that we recommend separating them into `<style>` tag.

```vue
<template>
  <!-- ✓ GOOD -->
  <div :style="styleObject"></div>
  <div :style="{ backgroundImage: 'url('+img+')' }"></div>

  <!-- ✗ BAD -->
  <div style="color: pink;"></div>
  <div :style="{ color: 'pink' }"></div>
  <div :style="[ { color: 'pink' }, { 'font-size': '85%' } ]"></div>
  <div :style="{ backgroundImage, color: 'pink' }"></div>
</template>
```

## Options

```json
{
  "vue/no-static-inline-styles": ["error", {
    "allowBinding": false
  }]
}
```

- allowBinding ... if `true`, allow binding static inline `style`. default `false`.

### `"allowBinding": true`

```vue
<template>
  <!-- ✓ GOOD -->
  <div :style="{ transform: 'scale(0.5)' }"></div>
  <div :style="[ { transform: 'scale(0.5)' }, { 'user-select': 'none' } ]"></div>

  <!-- ✗ BAD -->
  <div style="transform: scale(0.5);"></div>
</template>
```

## Further Reading

* [eslint-plugin-vue - no-static-inline-styles](https://eslint.vuejs.org/rules/no-static-inline-styles.html)
