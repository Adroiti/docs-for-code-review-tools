Pattern: Use of deprecated `.native` modifier on `v-on`

Issue: -

## Description

This rule reports use of deprecated `.native` modifier on `v-on` directive (in Vue.js 3.0.0+)

<eslint-code-block :rules="{'vue/no-deprecated-v-on-native-modifier': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <CoolInput v-on:keydown.enter="onKeydownEnter" />
  <CoolInput @keydown.enter="onKeydownEnter" />

  <!-- ✗ BAD -->
  <CoolInput v-on:keydown.native="onKeydown" />
  <CoolInput @keydown.enter.native="onKeydownEnter" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-v-on-native-modifier](https://eslint.vuejs.org/rules/no-deprecated-v-on-native-modifier.html)
* [Vue RFCs - 0031-attr-fallthrough](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0031-attr-fallthrough.md)
