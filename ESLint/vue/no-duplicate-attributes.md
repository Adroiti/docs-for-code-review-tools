Pattern: no duplicate attributes

Issue: -

## Description

This rule reports duplicate attributes.
`v-bind:foo` directives are handled as the attributes `foo`.

<eslint-code-block :rules="{'vue/no-duplicate-attributes': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent :foo="abc" />
  <MyComponent foo="abc" />
  <MyComponent class="abc" :class="def" />

  <!-- ✗ BAD -->
  <MyComponent :foo="abc" foo="def" />
  <MyComponent foo="abc" :foo="def" />
  <MyComponent foo="abc" foo="def" />
  <MyComponent :foo.a="abc" :foo.b="def" />
  <MyComponent class="abc" class="def" />
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-duplicate-attributes": ["error", {
    "allowCoexistClass": true,
    "allowCoexistStyle": true
  }]
}
```

- `allowCoexistClass` (`boolean`) ... Enables [`v-bind:class`] directive can coexist with the plain `class` attribute. Default is `true`.
- `allowCoexistStyle` (`boolean`) ... Enables [`v-bind:style`] directive can coexist with the plain `style` attribute. Default is `true`.

[`v-bind:class`]: https://vuejs.org/v2/guide/class-and-style.html
[`v-bind:style`]: https://vuejs.org/v2/guide/class-and-style.html

### `"allowCoexistClass": false, "allowCoexistStyle": false`

<eslint-code-block :rules="{'vue/no-duplicate-attributes': ['error', {allowCoexistClass: false, allowCoexistStyle: false}]}">

```vue
<template>
  <!-- ✗ BAD -->
  <MyComponent class="abc" :class="def" />
  <MyComponent style="abc" :style="def" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-duplicate-attributes](https://eslint.vuejs.org/rules/no-duplicate-attributes.html)
