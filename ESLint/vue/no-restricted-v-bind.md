Pattern: Use of restricted `v-bind` name

Issue: -

## Description

This rule allows you to specify `v-bind` argument names that you don't want to use in your application.

## Options

This rule takes a list of strings, where each string is a argument name or pattern to be restricted:

```json
{
  "vue/no-restricted-v-bind": ["error", "/^v-/", "foo", "bar"]
}
```

<eslint-code-block :rules="{'vue/no-restricted-v-bind': ['error', '/^v-/', 'foo', 'bar']}">

```vue
<template>
  <!-- ✗ BAD -->
  <div v-bind:foo="x" />
  <div :bar="x" />
</template>
```

</eslint-code-block>

By default, `'/^v-/'` is set. This prevents mistakes intended to be directives.

<eslint-code-block :rules="{'vue/no-restricted-v-bind': ['error']}">

```vue
<template>
  <!-- ✗ BAD -->
  <MyInput :v-model="x" />
  <div :v-if="x" />
</template>
```

</eslint-code-block>

Alternatively, the rule also accepts objects.

```json
{
  "vue/no-restricted-v-bind": ["error",
    {
      "argument": "/^v-/",
      "message": "Using `:v-xxx` is not allowed. Instead, remove `:` and use it as directive."
    },
    {
      "argument": "foo",
      "message": "Use \"v-bind:x\" instead."
    },
    {
      "argument": "bar",
      "message": "\":bar\" is deprecated."
    }
  ]
}
```

The following properties can be specified for the object.

- `argument` ... Specify the argument name or pattern or `null`. If `null` is specified, it matches `v-bind=`.
- `modifiers` ... Specifies an array of the modifier names. If specified, it will only be reported if the specified modifier is used.
- `element` ... Specify the element name or pattern. If specified, it will only be reported if used on the specified element.
- `message` ... Specify an optional custom message.

### `{ "argument": "foo", "modifiers": ["prop"]  }`

<eslint-code-block :rules="{'vue/no-restricted-v-bind': ['error', { argument: 'foo', modifiers: ['prop'] }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div :foo="x" />

  <!-- ✗ BAD -->
  <div :foo.prop="x" />
</template>
```

</eslint-code-block>

### `{ "argument": "foo", "element": "MyButton"  }`

<eslint-code-block :rules="{'vue/no-restricted-v-bind': ['error', { argument: 'foo', element: 'MyButton' }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <CoolButton :foo="x" />

  <!-- ✗ BAD -->
  <MyButton :foo="x" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-restricted-v-bind](https://eslint.vuejs.org/rules/no-restricted-v-bind.html)
