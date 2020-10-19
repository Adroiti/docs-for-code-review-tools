Pattern: Use of life-cycle hook after `await`

Issue: -

## Description

This rule reports the life-cycle hooks after `await` expression.  
In `setup()` function, `onXXX` life-cycle hooks should be registered synchronously.

<eslint-code-block :rules="{'vue/no-lifecycle-after-await': ['error']}">

```vue
<script>
import { onMounted } from 'vue'
export default {
  async setup() {
    /* ✓ GOOD */
    onMounted(() => { /* ... */ })

    await doSomething()

    /* ✗ BAD */
    onMounted(() => { /* ... */ })
  }
}
</script>
```

</eslint-code-block>

## :books: Further Reading


## Further Reading

* [eslint-plugin-vue - no-lifecycle-after-await](https://eslint.vuejs.org/rules/no-lifecycle-after-await.html)
* [Guide - Composition API - Lifecycle Hooks](https://v3.vuejs.org/guide/composition-api-lifecycle-hooks.html)
* [Vue RFCs - 0013-composition-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0013-composition-api.md)
