Pattern: Invalid attribute name on custom component

Issue: -

## Description

This rule enforces using hyphenated attribute names on custom components in Vue templates.

<eslint-code-block fix :rules="{'vue/attribute-hyphenation': ['error', 'always']}">

```vue
<template>
  <!-- ✔ GOOD -->
  <MyComponent my-prop="prop" />

  <!-- ✘ BAD -->
  <MyComponent myProp="prop" />
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/attribute-hyphenation": ["error", "always" | "never", {
    "ignore": []
  }]
}
```

Default casing is set to `always` with `['data-', 'aria-', 'slot-scope']` set to be ignored

- `"always"` (default) ... Use hyphenated name.
- `"never"` ... Don't use hyphenated name except `data-`, `aria-` and `slot-scope`.
- `"ignore"` ... Array of ignored names

### `"always"`
It errors on upper case letters.

<eslint-code-block fix :rules="{'vue/attribute-hyphenation': ['error', 'always']}">

```vue
<template>
  <!-- ✔ GOOD -->
  <MyComponent my-prop="prop" />

  <!-- ✘ BAD -->
  <MyComponent myProp="prop" />
</template>
```

</eslint-code-block>

### `"never"`
It errors on hyphens except `data-`, `aria-` and `slot-scope`.

<eslint-code-block fix :rules="{'vue/attribute-hyphenation': ['error', 'never']}">

```vue
<template>
  <!-- ✔ GOOD -->
  <MyComponent myProp="prop" />
  <MyComponent data-id="prop" />
  <MyComponent aria-role="button" />
  <MyComponent slot-scope="prop" />

  <!-- ✘ BAD -->
  <MyComponent my-prop="prop" />
</template>
```

</eslint-code-block>

### `"never", { "ignore": ["custom-prop"] }` 
Don't use hyphenated name but allow custom attributes

<eslint-code-block fix :rules="{'vue/attribute-hyphenation': ['error', 'never', { ignore: ['custom-prop']}]}">

```vue
<template>
  <!-- ✔ GOOD -->
  <MyComponent myProp="prop" />
  <MyComponent custom-prop="prop" />
  <MyComponent data-id="prop" />
  <MyComponent aria-role="button" />
  <MyComponent slot-scope="prop" />

  <!-- ✘ BAD -->
  <MyComponent my-prop="prop" />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - attribute-hyphenation](https://eslint.vuejs.org/rules/attribute-hyphenation.html)
