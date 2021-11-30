Pattern: Use of overridden child content

Issue: -

## Description

Reports child content of elements that have a directive which overwrites that child content. By default, those are `v-html` and `v-text`, additional ones (e.g. [Vue I18n's `v-t` directive](https://vue-i18n.intlify.dev/api/directive.html)) can be configured manually.

<eslint-code-block :rules="{'vue/no-child-content': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div>child content</div>
  <div v-html="replacesChildContent"></div>

  <!-- ✗ BAD -->
  <div v-html="replacesChildContent">child content</div>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-child-content": ["error", {
    "additionalDirectives": ["foo"] // checks v-foo directive
  }]
}
```

- `additionalDirectives` ... An array of additional directives to check, without the `v-` prefix. Empty by default; `v-html` and `v-text` are always checked.


## Further Reading

* [eslint-plugin-vue - no-child-content](https://eslint.vuejs.org/rules/no-child-content.html)
* [`v-html` directive](https://v3.vuejs.org/api/directives.html#v-html)
* [`v-text` directive](https://v3.vuejs.org/api/directives.html#v-text)
