Pattern: Use of `tag` attribute on `RouterLink` element

Issue: -

## Description

This rule reports deprecated the `tag` attribute on `RouterLink` elements (removed in Vue.js v3.0.0+).

<eslint-code-block :rules="{'vue/no-deprecated-router-link-tag-prop': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <RouterLink to="/">Home</RouterLink>
  <router-link to="/">Home</router-link>

  <RouterLink to="/">
    <div>Home</div>
  </RouterLink>

  <router-link to="/">
    <div>Home</div>
  </router-link>

  <NuxtLink tag="div" to="/">Home</NuxtLink>
  <nuxt-link tag="div" to="/">Home</nuxt-link>

  <!-- ✗ BAD -->
  <RouterLink tag="div" to="/">Home</RouterLink>
  <router-link tag="div" to="/">Home</router-link>
  <RouterLink :tag="someVariable" to="/">Home</RouterLink>
  <router-link :tag="someVariable" to="/">Home</router-link>
</template>
```

</eslint-code-block>

## Options

```json
{
  "vue/no-deprecated-router-link-tag-prop": ["error", {
    "components": ['RouterLink']
  }]
}
```

- `components` (`string[]`) ... Component names which will be checked with the `tag` attribute. default `['RouterLink']`.

Note: this rule will check both `kebab-case` and `PascalCase` versions of the
given component names.

### `{ "components": ['RouterLink', 'NuxtLink'] }`

<eslint-code-block :rules="{'vue/no-deprecated-router-link-tag-prop': ['error', {'components': ['RouterLink', 'NuxtLink']}]}">

```vue
<template>
  <!-- ✗ BAD -->
  <RouterLink tag="div" to="/">Home</RouterLink>
  <router-link tag="div" to="/">Home</router-link>

  <RouterLink :tag="someVariable" to="/">Home</RouterLink>
  <router-link :tag="someVariable" to="/">Home</router-link>

  <NuxtLink tag="div" to="/">Home</NuxtLink>
  <nuxt-link tag="div" to="/">Home</nuxt-link>

  <NuxtLink :tag="someVariable" to="/">Home</NuxtLink>
  <nuxt-link :tag="someVariable" to="/">Home</nuxt-link>
</template>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-deprecated-router-link-tag-prop](https://eslint.vuejs.org/rules/no-deprecated-router-link-tag-prop.html)
* [Vue RFCs - 0021-router-link-scoped-slot](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0021-router-link-scoped-slot.md)
