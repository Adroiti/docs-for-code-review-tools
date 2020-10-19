Pattern: Use of deprecated `KeyboardEvent.keyCode` modifier on `v-on`

Issue: -

## Description

This rule reports use of deprecated `KeyboardEvent.keyCode` modifier on `v-on` directive (in Vue.js 3.0.0+).

<eslint-code-block fix :rules="{'vue/no-deprecated-v-on-number-modifiers': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <input v-on:keyup.page-down="onArrowUp">
  <input @keyup.page-down="onArrowUp">
  <input @keyup.9="onArrowUp"> <!-- 9 is KeyboardEvent.key -->


  <!-- ✗ BAD -->
  <input v-on:keyup.34="onArrowUp">
  <input @keyup.34="onArrowUp">
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-v-on-number-modifiers](https://eslint.vuejs.org/rules/no-deprecated-v-on-number-modifiers.html)
* [Migration Guide - KeyCode Modifiers](https://v3.vuejs.org/guide/migration/keycode-modifiers.html)
* [Vue RFCs - 0014-drop-keycode-support](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0014-drop-keycode-support.md)
