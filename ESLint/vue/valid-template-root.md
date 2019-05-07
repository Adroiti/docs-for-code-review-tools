Pattern: valid template root

Issue: -

## Description

This rule reports the template root in the following cases:

<eslint-code-block :rules="{'vue/valid-template-root': ['error']}">

```vue
<!-- There is no root element -->
<template></template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/valid-template-root': ['error']}">

```vue
<!-- The root is text -->
<template>Lorem ipsum</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/valid-template-root': ['error']}">

```vue
<!-- There are multiple root elements -->
<template>
  <div>hello</div>
  <div>hello</div>
</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/valid-template-root': ['error']}">

```vue
<!-- The root element has `v-for` directives -->
<template>
  <div v-for="item in items"/>
</template>
```

</eslint-code-block>

<eslint-code-block :rules="{'vue/valid-template-root': ['error']}">

```vue
<!-- The root element is `<template>` or `<slot>` -->
<template>
  <slot />
</template>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - valid-template-root](https://eslint.vuejs.org/rules/valid-template-root.html)
