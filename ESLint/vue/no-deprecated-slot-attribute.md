Pattern: Use of deprecated `slot` attribute

Issue: -

## Description

This rule reports deprecated `slot` attribute in Vue.js v2.6.0+.

<eslint-code-block fix :rules="{'vue/no-deprecated-slot-attribute': ['error']}">

```vue
<template>
  <ListComponent>
    <!-- ✓ GOOD -->
    <template v-slot:name>
      {{ props.title }}
    </template>
  </ListComponent>
  <ListComponent>
    <!-- ✗ BAD -->
    <template slot="name">
      {{ props.title }}
    </template>
  </ListComponent>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-deprecated-slot-attribute](https://eslint.vuejs.org/rules/no-deprecated-slot-attribute.html)
