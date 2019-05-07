Pattern: no v html

Issue: -

## Description

This rule reports all uses of `v-html` directive in order to reduce the risk of injecting potentially unsafe / unescaped html into the browser leading to Cross-Site Scripting (XSS) attacks.

<eslint-code-block :rules="{'vue/no-v-html': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>{{ someHTML }}</div>

  <!-- ✗ BAD -->
  <div v-html="someHTML"></div>
</template>
```

</eslint-code-block>

## :mute: When Not To Use It

If you are certain the content passed to `v-html` is sanitized HTML you can disable this rule.

## Further Reading

* [eslint-plugin-vue - no-v-html](https://eslint.vuejs.org/rules/no-v-html.html)
