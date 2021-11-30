Pattern: Use of `expose()` after `await` 

Issue: -

## Description

Reports the `expose()` after `await` expression. In `setup()` function, `expose()` should be registered synchronously.

<eslint-code-block :rules="{'vue/no-expose-after-await': ['error']}">

```vue
<script>
import { watch } from 'vue'
export default {
  async setup(props, { expose }) {
    /* ✓ GOOD */
    expose({/* ... */})

    await doSomething()

    /* ✗ BAD */
    expose({/* ... */})
  }
}
</script>
```

</eslint-code-block>


## Further Reading

* [eslint-plugin-vue - no-expose-after-await](https://eslint.vuejs.org/rules/no-expose-after-await.html)
* [Vue RFCs - 0042-expose-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0042-expose-api.md)
* [Vue RFCs - 0013-composition-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0013-composition-api.md)
