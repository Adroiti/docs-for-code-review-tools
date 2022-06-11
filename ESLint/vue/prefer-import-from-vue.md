Pattern: Missing use of `'vue'` import

Issue: -

## Description

This rule aims to use imports from `'vue'` instead of imports from `'@vue/*'`.

Imports from the following modules are almost always wrong. You should import from `vue` instead.

- `@vue/runtime-dom`
- `@vue/runtime-core`
- `@vue/reactivity`
- `@vue/shared`

<eslint-code-block fix :rules="{'vue/prefer-import-from-vue': ['error']}" filename="example.js" language="javascript">

```js
/* ✓ GOOD */
import { createApp, ref, Component } from 'vue'
```

</eslint-code-block>

<eslint-code-block fix :rules="{'vue/prefer-import-from-vue': ['error']}" filename="example.js" language="javascript">

```js
/* ✗ BAD */
import { createApp } from '@vue/runtime-dom'
import { Component } from '@vue/runtime-core'
import { ref } from '@vue/reactivity'
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - prefer-import-from-vue](https://eslint.vuejs.org/rules/prefer-import-from-vue.html)
