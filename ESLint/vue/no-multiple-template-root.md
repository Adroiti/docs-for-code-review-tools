Pattern: Use of multiple root nodes in template

Issue: -

## Description

This rule checks whether template contains single root element valid for Vue 2.

<eslint-code-block :rules="{'vue/no-multiple-template-root': ['error']}">

```vue
<!-- The root is text -->
<template>Lorem ipsum</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-multiple-template-root': ['error']}">

```vue
<!-- There are multiple root elements -->
<template>
  <div>hello</div>
  <div>hello</div>
</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-multiple-template-root': ['error']}">

```vue
<!-- The root element has `v-for` directives -->
<template>
  <div v-for="item in items"/>
</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/no-multiple-template-root': ['error']}">

```vue
<!-- The root element is `<template>` or `<slot>` -->
<template>
  <slot />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-multiple-template-root](https://eslint.vuejs.org/rules/no-multiple-template-root.html)
