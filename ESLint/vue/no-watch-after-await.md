Pattern: Use of `watch()` after `await` expression

Issue: -

## Description

This rule reports the `watch()` after `await` expression.  
In `setup()` function, `watch()` should be registered synchronously.

<eslint-code-block :rules="{'vue/no-watch-after-await': ['error']}">

```vue
<script>
import { watch } from 'vue'
export default {
  async setup() {
    /* ✓ GOOD */
    watch(watchSource, () => { /* ... */ })

    await doSomething()

    /* ✗ BAD */
    watch(watchSource, () => { /* ... */ })
  }
}
</script>
```

</eslint-code-block>

This rule is not reported when using the stop handle.

<eslint-code-block :rules="{'vue/no-watch-after-await': ['error']}">

```vue
<script>
import { watch } from 'vue'
export default {
  async setup() {
    await doSomething()

    /* ✓ GOOD */
    const stopHandle = watch(watchSource, () => { /* ... */ })

    // later
    stopHandle()
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-watch-after-await](https://eslint.vuejs.org/rules/no-watch-after-await.html)
* [Guide - Reactivity - Computed and Watch](https://v3.vuejs.org/guide/reactivity-computed-watchers.html)
* [Vue RFCs - 0013-composition-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0013-composition-api.md)

