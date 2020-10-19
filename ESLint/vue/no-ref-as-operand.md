Pattern: Use of `ref` as operand

Issue: -

## Description

This rule reports cases where a ref is used incorrectly as an operand.  
You must use `.value` to access the `ref` value.

<eslint-code-block :rules="{'vue/no-ref-as-operand': ['error']}">

```vue
<script>
import { ref } from 'vue'

export default {
  setup () {
    const count = ref(0)
    const ok = ref(true)

    /* ✓ GOOD */
    count.value++
    count.value + 1
    1 + count.value
    var msg = ok.value ? 'yes' : 'no'

    /* ✗ BAD */
    count++
    count + 1
    1 + count
    var msg = ok ? 'yes' : 'no'

    return {
      count
    }
  }
}
</script>
```

</eslint-code-block>

## Further Reading

* [eslint-plugin-vue - no-ref-as-operand](https://eslint.vuejs.org/rules/no-ref-as-operand.html)
* [Guide - Reactivity - Reactivity Fundamentals / Creating Standalone Reactive Values as `refs`](https://v3.vuejs.org/guide/reactivity-fundamentals.html#creating-standalone-reactive-values-as-refs)
* [Vue RFCs - 0013-composition-api](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0013-composition-api.md)
