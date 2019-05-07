Pattern: valid v on

Issue: -

## Description

This rule reports `v-on` directives in the following cases:

- The directive does not have that event name. E.g. `<div v-on="foo"></div>`
- The directive has invalid modifiers. E.g. `<div v-on:click.bbb="foo"></div>`
- The directive does not have that attribute value and any verb modifiers. E.g. `<div v-on:click></div>`

<eslint-code-block :rules="{'vue/valid-v-on': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div v-on="foo"/>
  <div v-on:click="foo"/>
  <div @click="foo"/>
  <div @click.left="foo"/>
  <div @click.prevent/>
  <div @click.stop/>

  <!-- ✗ BAD -->
  <div v-on/>
  <div v-on:click/>
  <div v-on:click.aaa="foo"/>
  <div @click/>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/valid-v-on": ["error", {
    "modifiers": []
  }]
}
```

This rule has an object option:

`"modifiers"` array of additional allowed modifiers.

### `"modifiers": ["foo"]`

<eslint-code-block :rules="{'vue/valid-v-on': ['error', { modifiers: ['foo']}]}">

```vue
<template>
  <div @click.foo="foo"/>
  <div v-on:click.foo="foo"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-v-on](https://eslint.vuejs.org/rules/valid-v-on.html)
