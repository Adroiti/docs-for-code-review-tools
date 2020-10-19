Pattern: Use of insecure `target="_blank"`

Issue: -

## Description

This rule disallows using `target="_blank"` attribute without `rel="noopener noreferrer"` to avoid a security vulnerability([see here for more details](https://mathiasbynens.github.io/rel-noopener/)).

<eslint-code-block :rules="{'vue/no-template-target-blank': ['error']}">

```vue
<template>
  <!-- ✓ Good -->
  <a href="http://example.com" target="_blank" rel="noopener noreferrer">link</a>

  <!-- ✗ BAD -->
  <a href="http://example.com" target="_blank" >link</a>
</temlate>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-template-target-blank": ["error", {
    "allowReferrer": true,
    "enforceDynamicLinks": "always"
  }]
}
```

- `allowReferrer` ... If `true`, does not require noreferrer.default `false`
- `enforceDynamicLinks ("always" | "never")` ... If `always`, enforces the rule if the href is a dynamic link. default `always`.

### `{ allowReferrer: false }` (default)

<eslint-code-block :rules="{'vue/no-template-target-blank': ['error', { allowReferrer: false }]}">

```vue
<template>
  <!-- ✓ Good -->
  <a href="http://example.com" target="_blank" rel="noopener noreferrer">link</a>

  <!-- ✗ BAD -->
  <a href="http://example.com" target="_blank" rel="noopener">link</a>
</temlate>
```

</eslint-code-block>

### `{ allowReferrer: true }`

<eslint-code-block :rules="{'vue/no-template-target-blank': ['error', { allowReferrer: true }]}">

```vue
<template>
  <!-- ✓ Good -->
  <a href="http://example.com" target="_blank" rel="noopener">link</a>

  <!-- ✗ BAD -->
  <a href="http://example.com" target="_blank" >link</a>
</temlate>
```

</eslint-code-block>

### `{ "enforceDynamicLinks": "always" }` (default)

<eslint-code-block :rules="{'vue/no-template-target-blank': ['error', { enforceDynamicLinks: 'always' }]}">

```vue
<template>
  <!-- ✓ Good -->
  <a :href="link" target="_blank" rel="noopener noreferrer">link</a>

  <!-- ✗ BAD -->
  <a :href="link" target="_blank">link</a>
</temlate>
```

</eslint-code-block>

### `{ "enforceDynamicLinks": "never" }`

<eslint-code-block :rules="{'vue/no-template-target-blank': ['error', { enforceDynamicLinks: 'never' }]}">

```vue
<template>
  <!-- ✓ Good -->
  <a :href="link" target="_blank">link</a>

  <!-- ✗ BAD -->
  <a href="http://example.com" target="_blank" >link</a>
</temlate>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-template-target-blank](https://eslint.vuejs.org/rules/no-template-target-blank.html)
