Pattern: Malformed `v-slot` directive

Issue: -

## Description

This rule reports `v-slot` directives in the following cases:

- The directive is not owned by a custom element. E.g. `<div v-slot=""></div>`
- The directive is a named slot and is on a custom element directly. E.g. `<my-component v-slot:foo></my-component>`
- The directive is the default slot, is on a custom element directly, and there are other named slots. E.g. `<my-component v-slot=""><template v-slot:foo></template></my-component>`
- The element which has the directive has another `v-slot` directive. E.g. `<my-component v-slot:one v-slot:two></my-component>`
- The element which has the directive has another `v-slot` directive that is distributed to the same slot. E.g. `<my-component><template v-slot:foo></template><template v-slot:foo></template></my-component>`
- The directive has a dynamic argument which uses the scope properties that the directive defined. E.g. `<my-component><template v-slot:[data]="data"></template></my-component>`
- The directive has any modifier. E.g. `<my-component v-slot.foo></my-component>`
- The directive is the default slot, is on a custom element directly, and has no value. E.g. `<my-component v-slot></my-component>`

<eslint-code-block :rules="{'vue/valid-v-slot': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <my-component v-slot="data">
    {{data}}
  </my-component>
  <my-component>
    <template v-slot:default>
      default
    </template>
    <template v-slot:one>
      one
    </template>
    <template v-slot:two>
      two
    </template>
  </my-component>

  <!-- ✗ BAD -->
  <div v-slot="data">
    {{data}}
  </div>
  <div>
    <template v-slot:one>
      one
    </template>
  </div>

  <my-component v-slot:one="data">
    {{data}}
  </my-component>
  <my-component v-slot="data">
    {{data}}
    <template v-slot:one>
      one
    </template>
  </my-component>

  <my-component v-slot:one v-slot:two>
    one and two
  </my-component>
  <my-component>
    <template v-slot:one>
      one 1
    </template>
    <template v-slot:one>
      one 2
    </template>
  </my-component>

  <my-component>
    <template v-slot:[data]="data">
      dynamic?
    </template>
  </my-component>

  <my-component v-slot.mod="data">
    {{data}}
  </my-component>

  <my-component v-slot>
    content
  </my-component>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-slot](https://eslint.vuejs.org/rules/valid-v-slot.html)
