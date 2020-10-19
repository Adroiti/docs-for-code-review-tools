Pattern: Use of deprecated `$scopedSlots`

Issue: -

## Description

This rule reports use of deprecated `$scopedSlots`. (in Vue.js 3.0.0+).

<eslint-code-block fix :rules="{'vue/no-deprecated-dollar-scopedslots-api': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div v-if="$scopedSlots.default"><slot /></div>
</template>
<script>
export default {
  render() {
    /* ✗ BAD */
    return this.$scopedSlots.default()
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-dollar-scopedslots-api](https://eslint.vuejs.org/rules/no-deprecated-dollar-scopedslots-api.html)
* [Migration Guide - Slots Unification](https://v3.vuejs.org/guide/migration/slots-unification.html)
* [Vue RFCs - 0006-slots-unification](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0006-slots-unification.md)