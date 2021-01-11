Pattern: Missing use of hyphenated v-on event name

Issue: -

## Description

This rule enforces using hyphenated v-on event names on custom components in Vue templates.

<eslint-code-block fix :rules="{'vue/v-on-event-hyphenation': ['error', 'always', { autofix: true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-on:custom-event="handleEvent"/>
  <MyComponent @custom-event="handleEvent"/>

  <!-- ✗ BAD -->
  <MyComponent v-on:customEvent="handleEvent"/>
  <MyComponent @customEvent="handleEvent"/>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/v-on-event-hyphenation": ["error", "always" | "never", {
    "autofix": false,
    "ignore": []
  }]
}
```

- `"always"` (default) ... Use hyphenated name.
- `"never"` ... Don't use hyphenated name.
- `"ignore"` ... Array of ignored names
- `"autofix"` ... If `true`, enable autofix. If you are using Vue 2, we recommend that you do not use it due to its side effects.

### `"always"`

It errors on upper case letters.

<eslint-code-block fix :rules="{'vue/v-on-event-hyphenation': ['error', 'always', { autofix: true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-on:custom-event="handleEvent"/>

  <!-- ✗ BAD -->
  <MyComponent v-on:customEvent="handleEvent"/>
</template>
```

</eslint-code-block>

### `"never"`

It errors on hyphens.

<eslint-code-block fix :rules="{'vue/v-on-event-hyphenation': ['error', 'never', { autofix: true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-on:customEvent="handleEvent"/>

  <!-- ✗ BAD -->
  <MyComponent v-on:custom-event="handleEvent"/>
</template>
```

</eslint-code-block>

### `"never", { "ignore": ["custom-event"] }`

Don't use hyphenated name but allow custom event names

<eslint-code-block fix :rules="{'vue/v-on-event-hyphenation': ['error', 'never', { ignore: ['custom-event'], autofix: true }]}">

```vue
<template>
  <!-- ✓ GOOD -->
  <MyComponent v-on:custom-event="handleEvent"/>
  <MyComponent v-on:myEvent="handleEvent"/>

  <!-- ✗ BAD -->
  <MyComponent v-on:my-event="handleEvent"/>
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - v-on-event-hyphenation](https://eslint.vuejs.org/rules/v-on-event-hyphenation.html)
