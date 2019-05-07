Pattern: component name in template casing

Issue: -

## Description

This rule aims to warn the tag names other than the configured casing in Vue.js template.

## Options

```json
{
  "vue/component-name-in-template-casing": ["error", "PascalCase" | "kebab-case", {
    "registeredComponentsOnly": true,
    "ignores": []
  }]
}
```

- `"PascalCase"` (default) ... enforce tag names to pascal case. E.g. `<CoolComponent>`. This is consistent with the JSX practice.
- `"kebab-case"` ... enforce tag names to kebab case: E.g. `<cool-component>`. This is consistent with the HTML practice which is case-insensitive originally.
- `registeredComponentsOnly` ... If `true`, only registered components (in PascalCase) are checked. If `false`, check all.
    default `true`
- `ignores` (`string[]`) ... The element names to ignore. Sets the element name to allow. For example, custom elements or Vue components with special name. You can set the regexp by writing it like `"/^name/"`.

### `"PascalCase", { registeredComponentsOnly: true }` (default)

<eslint-code-block fix :rules="{'vue/component-name-in-template-casing': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <CoolComponent />
  
  <!-- ✗ BAD -->
  <cool-component />
  <coolComponent />
  <Cool-component />

  <!-- ignore -->
  <UnregisteredComponent />
  <unregistered-component />

  <registered-in-kebab-case />
  <registeredInCamelCase />
</template>
<script>
export default {
  components: {
    CoolComponent,
    'registered-in-kebab-case': VueComponent1,
    'registeredInCamelCase': VueComponent2
  }
}
</script>
```

</eslint-code-block>

### `"kebab-case"`

<eslint-code-block fix :rules="{'vue/component-name-in-template-casing': ['error', 'kebab-case']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <cool-component />

  <!-- ✗ BAD -->
  <CoolComponent />
  <coolComponent />
  <Cool-component />

  <!-- ignore -->
  <unregistered-component />
  <UnregisteredComponent />
</template>
<script>
export default {
  components: {
    CoolComponent
  }
}
</script>
```

</eslint-code-block>

### `"PascalCase", { registeredComponentsOnly: false }`

<eslint-code-block fix :rules="{'vue/component-name-in-template-casing': ['error', 'PascalCase', { registeredComponentsOnly: false }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <CoolComponent />
  <UnregisteredComponent />
  
  <!-- ✗ BAD -->
  <cool-component />
  <unregistered-component />
</template>
<script>
export default {
  components: {
    CoolComponent
  }
}
</script>
```

</eslint-code-block>

### `"PascalCase", { ignores: ["/^custom-/"], registeredComponentsOnly: false }`

<eslint-code-block fix :rules="{'vue/component-name-in-template-casing': ['error', 'PascalCase', {ignores: ['/^custom-/'], registeredComponentsOnly: false}]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <CoolComponent/>
  <custom-element></custom-element>
  <custom-button></custom-button>
  <custom-input />
  
  <!-- ✗ BAD -->
  <magic-element></magic-element>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - component-name-in-template-casing](https://eslint.vuejs.org/rules/component-name-in-template-casing.html)
