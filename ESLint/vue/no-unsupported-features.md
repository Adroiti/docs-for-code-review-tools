Pattern: Unsupported _Vue.js_ syntax

Issue: -

## Description

This rule reports unsupported Vue.js syntax on the specified version.

## Options

```json
{
  "vue/no-unsupported-features": ["error", {
    "version": "^2.6.0",
    "ignores": []
  }]
}
```

- `version` ... The `version` option accepts [the valid version range of `node-semver`](https://github.com/npm/node-semver#range-grammar). Set the version of Vue.js you are using. This option is required.
- `ignores` ... You can use this `ignores` option to ignore the given features.
The `"ignores"` option accepts an array of the following strings.
  - Vue.js 2.6.0+
    - `"dynamic-directive-arguments"` ... [dynamic directive arguments](https://vuejs.org/v2/guide/syntax.html#Dynamic-Arguments).
    - `"v-slot"` ... [v-slot](https://vuejs.org/v2/api/#v-slot) directive.
  - Vue.js 2.5.0+
    - `"slot-scope-attribute"` ... [slot-scope](https://vuejs.org/v2/api/#slot-scope-deprecated) attributes.
  - Vue.js `">=2.6.0-beta.1 <=2.6.0-beta.3"` or 2.6 custom build
    - `"v-bind-prop-modifier-shorthand"` ... [v-bind](https://vuejs.org/v2/api/#v-bind) with `.prop` modifier shorthand.

### `{"version": "^2.5.0"}`

```vue
<template>
  <!-- ✓ GOOD -->
  <CustomComponent :foo="val" />
  <ListComponent>
    <template slot="name" slot-scope="props">
      {{ props.title }}
    </template>
  </ListComponent>

  <!-- ✗ BAD -->
  <!-- dynamic directive arguments -->
  <CustomComponent :[foo]="val" />
  <ListComponent>
    <!-- v-slot -->
    <template v-slot:name="props">
      {{ props.title }}
    </template>
    <template #name="props">
      {{ props.title }}
    </template>
  </ListComponent>
</template>
```

## Further Reading

* [eslint-plugin-vue - no-unsupported-features](https://eslint.vuejs.org/rules/no-unsupported-features.html)
