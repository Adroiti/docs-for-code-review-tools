Pattern: Missing shorthand use of `v-bind` attribute with `true`

Issue: -

## Description

`v-bind` attribute with `true` value usually can be written in shorthand form. This can reduce verbosity.

<eslint-code-block :rules="{'vue/prefer-true-attribute-shorthand': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <MyComponent v-bind:show="true" />
  <MyComponent :show="true" />

  <!-- ✓ GOOD -->
  <MyComponent show />
  <MyComponent another-prop="true" />
</template>
```

</eslint-code-block>

::: warning Warning
The shorthand form is not always equivalent! If a prop accepts multiple types, but Boolean is not the first one, a shorthand prop won't pass `true`.
:::

```vue
<script>
export default {
  name: 'MyComponent',
  props: {
    bool: Boolean,
    boolOrString: [Boolean, String],
    stringOrBool: [String, Boolean],
  }
}
</script>
```

**Shorthand form:**

```vue
<MyComponent bool bool-or-string string-or-bool />
```

```plain
bool: true (boolean)
boolOrString: true (boolean)
stringOrBool: "" (string)
```

**Longhand form:**

```vue
<MyComponent :bool="true" :bool-or-string="true" :string-or-bool="true" />
```

```plain
bool: true (boolean)
boolOrString: true (boolean)
stringOrBool: true (boolean)
```

Those two calls will introduce different render result.

## Options

Default options is `"always"`.

```json
{
  "vue/prefer-true-attribute-shorthand": ["error", "always" | "never"]
}
```

- `"always"` (default) ... requires shorthand form.
- `"never"` ... requires long form.

### `"never"`

<eslint-code-block :rules="{'vue/prefer-true-attribute-shorthand': ['error', 'never']}">

```vue
<template>
  <!-- ✗ BAD -->
  <MyComponent show />

  <!-- ✓ GOOD -->
  <MyComponent :show="true" />
  <MyComponent v-bind:show="true" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - prefer-true-attribute-shorthand](https://eslint.vuejs.org/rules/prefer-true-attribute-shorthand.html)
