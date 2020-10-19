Pattern: Use of bare string in `<template>`

Issue: -

## Description

In order to be able to internationalize your application, you will need to avoid using plain strings in your templates. Instead, you would need to use a template helper specializing in translation.  

<eslint-code-block :rules="{'vue/no-bare-strings-in-template': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <h1>{{ $t('foo.bar') }}</h1>
  <h1>{{ foo }}</h1>
  <h1 v-t="'foo.bar'"></h1>

  <!-- ✗ BAD -->
  <h1>Lorem ipsum</h1>
  <div
    title="Lorem ipsum"
    aria-label="Lorem ipsum"
    aria-placeholder="Lorem ipsum"
    aria-roledescription="Lorem ipsum"
    aria-valuetext="Lorem ipsum"
  />
  <img alt="Lorem ipsum">
  <input placeholder="Lorem ipsum">
  <h1 v-text="'Lorem ipsum'" />

  <!-- Does not check -->
  <h1>{{ 'Lorem ipsum' }}</h1>
  <div
    v-bind:title="'Lorem ipsum'"
  />
</template>
```

</eslint-code-block>

:::tip
This rule does not check for string literals, in bindings and mustaches interpolation. This is because it looks like a conscious decision.  
If you want to report these string literals, enable the [vue/no-useless-v-bind] and [vue/no-useless-mustaches] rules and fix the useless string literals.
:::

## Options

```js
{
  "vue/no-bare-strings-in-template": ["error", {
    "allowlist": [
      "(", ")", ",", ".", "&", "+", "-", "=", "*", "/", "#", "%", "!", "?", ":", "[", "]", "{", "}", "<", ">", "\u00b7", "\u2022", "\u2010", "\u2013", "\u2014", "\u2212", "|"
    ],
    "attributes": {
      "/.+/": ["title", "aria-label", "aria-placeholder", "aria-roledescription", "aria-valuetext"],
      "input": ["placeholder"],
      "img": ["alt"]
    },
    "directives": ["v-text"]
  }]
}
```

- `allowlist` ... An array of allowed strings.
- `attributes` ... An object whose keys are tag name or patterns and value is an array of attributes to check for that tag name.
- `directives` ... An array of directive names to check literal value.

## Further Reading

* [eslint-plugin-vue - no-bare-strings-in-template](https://eslint.vuejs.org/rules/no-bare-strings-in-template.html)
